# Componentization

In Rocket.Chat, a component is a reusable piece of code that represents a single UI element. Components can be [**simple**](componentization.md#simple-components) or [**complex**](componentization.md#complex-components) and [**visual** ](componentization.md#visual-components)or [**logical**](componentization.md#logical-components). There are various guidelines governing each component type.

These components can either live on the **Application** or the **Fuselage** library.

* **Application components** are specific to a particular Rocket.Chat application. They are not reusable across applications.
* **Fuselage library components** are reusable across all Rocket.Chat applications. They are the recommended way to create components for Rocket.Chat applications.

**Components Rules Matrix**

The components rules matrix includes the table below:

|                   | Fuselage Level | Application Level |
| ----------------- | -------------- | ----------------- |
| Simple & Visual   | ✅              | ❌                 |
| Complex & Visual  | ✅              | ✅                 |
| Simple & Logical  | ❌              | ❌                 |
| Complex & Logical | ❌              | ✅                 |

### Simple Components

These are the lowest level of components. They represent a single, atomic UI element in the interface, such as a `button` component or a text field.

1. **Variation over Styles**

Use prop names that suggest the variation of a component, rather than using style-based prop names. For example, instead of using a prop name like `color` with a value of `blue`, you could use a prop name like `variation` with a value of `primary`. This makes the code more readable and maintainable, and it also makes it easier to create consistent and reusable components.

![](https://user-images.githubusercontent.com/27704687/186257526-a3bce55a-3eeb-4815-9bf0-569e79528f5f.png)

2. **Avoid using hardcoded values or magic numbers**.&#x20;

✅ **Preferred exampl**e: Use the 'small' and 'square' props to dynamically adjust the component size.

```jsx
<Button small square>
    <Icon name='circle-arrow-down' size='x24' />
</Button>
```

❌ Not recommended: Defining component size using specific numeric values.

```jsx
<Button height='50px' width='50px' square>
    <Icon name='circle-arrow-down' size='x24' />
</Button>
```

3. **Opt for Customization via CSS Variables**

Avoid the use of random CSS values and instead, prioritize customization by utilizing CSS variables.

```scss
$modal-margin: theme('modal-margin', auto);

.rcx-modal {
    position: static;
    
    display: flex;
    
    width: 100%;
    max-height: 100%;
    margin: $modal-margin;
}
```

4. **Document and Display All Variations in Storybook**

Ensure that all possible variations are documented and showcased within the Storybook. This enables developers and designers to explore the full range of available options. Additionally, include descriptive explanations for variations that might not be self-explanatory.

![Screen Shot 2022-08-23 at 17 31 17](https://user-images.githubusercontent.com/27704687/186259765-4ee6e5e1-da1f-439b-aaac-05683714f75f.png)

5. **Unit Testing for All Possible Component Behaviors**

Ensure comprehensive coverage of all intended component behaviors through unit tests. It's crucial to highlight the importance of writing unit tests that cover all possible scenarios and functionalities of the component. This practice helps ensure the reliability and correctness of the codebase.

```tsx
describe('[Menu Component]', () => {
  const menuOption = screen.queryByText('Make Admin');

  it('should renders without crashing', () => {
    render(<Simple {...Simple.args} />);
  });

  it('should open options when click', async () => {
    const { getByTestId } = render(<Simple {...Simple.args} />);
    const button = getByTestId('menu');
    userEvent.click(button);
    expect(await screen.findByText('Make Admin')).toBeInTheDocument();
  });

  it('should have no options when click twice', async () => {
    const { getByTestId } = render(<Simple {...Simple.args} />);
    const button = getByTestId('menu');
    userEvent.click(button);
    userEvent.click(button);
    expect(menuOption).toBeNull();
  });

  it('should have no options when click on menu and then elsewhere', async () => {
    const { getByTestId } = render(<Simple {...Simple.args} />);
    const button = getByTestId('menu');
    userEvent.click(button);
    userEvent.click(document.body);
    expect(menuOption).toBeNull();
  });
});
```

6. **Avoid Box Component**

The usage of `Box` is recommended for Simple or Complex Components **mainly** (save the cases when we need to quickly prototype a component) on the Application Level as it's a wildcard component, for simple components, we suggest avoiding it and building the component using HTML tags

### Complex Components

**Complex components** are made up of multiple simple components. They can be used to create more complex UI elements, such as a modal or a table.

1. **Only visual, no logic**

Concentrate solely on the user interface design, ensuring it is poised to incorporate the required logic seamlessly .

![](https://user-images.githubusercontent.com/27704687/186262142-bb6a3354-d1f4-410d-bde9-6640bd7ccbcd.png)

2. **Split the component in an easy to understanding way**

```tsx
export const Default = () => {
    <Modal>
        <Modal.Header>
            <Modal.HeaderText>
                <Modal.Title>Modal Header</Modal.Title>
            </Modal.HeaderText>
            <Modal.Close />
        </Modal.Header>
        <Modal.Content>Modal Body</Modal.Content>
        <Modal.Footer>
            <Modal.FooterControllers>
                <Button>Cancel</Button>
                <Button primary onClick={action('click')}>
                    Submit
                </Button>
            </Modal.FooterControllers>
        </Modal.Footer>
    </Modal>
};
```

3. **Initiate your development process by adopting Storybook, which facilitates the separation of logic from the user interface.**

```tsx
export const CallingDM: ComponentStory<typeof VideoConfMessage> = () => (
	<VideoConfMessage>
		<VideoConfMessageRow>
			<VideoConfMessageIcon variant='incoming' />
			<VideoConfMessageText>Calling...</VideoConfMessageText>
		</VideoConfMessageRow>
		<VideoConfMessageFooter>
			<VideoConfMessageAction primary>Join</VideoConfMessageAction>
			<VideoConfMessageFooterText>Waiting for answer</VideoConfMessageFooterText>
		</VideoConfMessageFooter>
	</VideoConfMessage>
);

export const CallEndedDM: ComponentStory<typeof VideoConfMessage> = () => (
	<VideoConfMessage>
		<VideoConfMessageRow>
			<VideoConfMessageIcon />
			<VideoConfMessageText>Call ended</VideoConfMessageText>
		</VideoConfMessageRow>
		<VideoConfMessageFooter>
			<VideoConfMessageAction>Call Back</VideoConfMessageAction>
			<VideoConfMessageFooterText>Call was not answered</VideoConfMessageFooterText>
		</VideoConfMessageFooter>
	</VideoConfMessage>
);
```

4. **Child Components can't be used outside of the scope**

❌ Incorrect example of component composition:

```jsx
export const MyComponent: ComponentStory<typeof VideoConfMessage> = () => (
    <Box display='flex'>
        <form>
            <VideoConfMessageAction>Call ended</VideoConfMessageAction>
        </form>
    </Box>
);
```

✅ Correct example of component composition:

```jsx
export const MyComponent: ComponentStory<typeof VideoConfMessage> = () => (
    <Box display='flex'>
        <form>
            <VideoConfMessage>
                <VideoConfMessageFooter>
                    <VideoConfMessageAction>Call ended</VideoConfMessageAction>
                </VideoConfMessageFooter>
            </VideoConfMessage>
        </form>
    </Box>
);
```

5. **HTML elements, Box, and Box props should be encapsulated**

Encapsulation is a valuable software design principle that enhances code quality. By defining clear responsibilities for components, it improves understanding, maintenance, and testing.

In the context of HTML elements, Box components, and Box props, encapsulation means accessing them solely through the Box component's API. This prevents unintended modifications to the Box component's internal state, ensuring predictable behavior and streamlined debugging.

❌ Incorrect example of component composition:

{% code overflow="wrap" %}
```tsx
export const VideoConfMessage: ComponentStory<typeof VideoConfMessage> = () => (
    <Box mbs='x4' maxWidth='345px' borderWidth={2} borderColor='neutral-200' borderRadius='x4'>
        <Box p='x16' display='flex' alignItems='center'>
            <Icon name='link' />
            <div>My Text</div>
        </Box>
    </Box>
);
```
{% endcode %}

✅ Correct example of component composition:

{% code overflow="wrap" %}
```tsx
const VideoConfMessage = ({ ...props }): ReactElement => (
    <Box mbs='x4' maxWidth='345' borderWidth={2} borderColor='neutral-200' borderRadius='x4' {...props}  />
);
```
{% endcode %}

6. **Provide Hooks as Helpers**

In the following example, the **useVideoConfControllers** hook is provided as a helper to manage the state of the popup's controllers.

```tsx
export const useVideoConfControllers = (
	initialPreferences: controllersConfigProps = { mic: true, cam: false },
): { controllersConfig: controllersConfigProps; handleToggleMic: () => void; handleToggleCam: () => void } => {
	const [controllersConfig, setControllersConfig] = useState(initialPreferences);

	const handleToggleMic = useCallback((): void => {
		setControllersConfig((prevState) => ({ ...prevState, mic: !prevState.mic }));
	}, []);

	const handleToggleCam = useCallback((): void => {
		setControllersConfig((prevState) => ({ ...prevState, cam: !prevState.cam }));
	}, []);

	return {
		controllersConfig,
		handleToggleMic,
		handleToggleCam,
	};
};
```

```tsx
const { controllersConfig } = useVideoConfControllers();

return (
	<VideoConfPopup>
		<VideoConfPopupHeader>
			<VideoConfPopupTitle text={t('Calling')} counter />
			<VideoConfPopupControllers>
				<VideoConfController
					active={controllersConfig.cam}
					title={controllersConfig.cam ? t('Cam_on') : t('Cam_off')}
					icon={controllersConfig.cam ? 'video' : 'video-off'}
					disabled
				/>
				<VideoConfController
					active={controllersConfig.mic}
					title={controllersConfig.mic ? t('Mic_on') : t('Mic_off')}
					icon={controllersConfig.mic ? 'mic' : 'mic-off'}
					disabled
				/>
			</VideoConfPopupControllers>
		</VideoConfPopupHeader>
	</VideoConfPopup>
);
```

7. **Understanding the component and defining the scope**

New components typically emerge from requirements put forth by the Product Design Team. The front-end engineer holds the responsibility of assessing the genuine necessity of such components. Due to the substantial effort involved in creating a new component, it is prudent to collaborate with product managers and designers. It is advisable to explore the feasibility of employing Complex Components as an MVP to validate concepts and user flows. Subsequent to successful validation, the progression to developing a new Fuselage Level component can be considered.

{% hint style="warning" %}
How do I know my component should be part of the Fuselage library?
{% endhint %}

Consider the `VerticalBar` component as a clear example. It began as a Complex Component for a single application but has now advanced to the Fuselage Level. This shift is driven by its usefulness in multiple applications, like Rocket.Chat and Cloud Portal. This case demonstrates how components can grow from specific solutions to versatile tools with broader applications.

### Logical Components

1. **Use the child components to compose a logical complex component**

Leverage the integration of child components to construct a unified and logical complex component.

```tsx
const OutgoingPopup = ({ room, onClose, id }: OutgoingPopupProps): ReactElement => {
	const t = useTranslation();
	const videoConfPreferences = useVideoConfPreferences();
	const { controllersConfig } = useVideoConfControllers();
	
	return (
		<VideoConfPopup>
			<VideoConfPopupHeader>
				<VideoConfPopupTitle text={t('Calling')} counter />
				<VideoConfPopupControllers>
					<VideoConfController
						active={controllersConfig.cam}
						title={controllersConfig.cam ? t('Cam_on') : t('Cam_off')}
						icon={controllersConfig.cam ? 'video' : 'video-off'}
						disabled
					/>
					<VideoConfController
						active={controllersConfig.mic}
						title={controllersConfig.mic ? t('Mic_on') : t('Mic_off')}
						icon={controllersConfig.mic ? 'mic' : 'mic-off'}
						disabled
					/>
				</VideoConfPopupControllers>
			</VideoConfPopupHeader>
		</VideoConfPopup>
	);
}
```

2. **Customization through the variations**

Provide users with the ability to customize a component's appearance or behavior by selecting from predefined variations or options. This approach enhances user experience and flexibility in adapting components to specific requirements.

<pre class="language-tsx"><code class="lang-tsx">&#x3C;VideoConfController
<strong>    active={controllersConfig.mic}
</strong>    title={controllersConfig.mic ? t('Mic_on') : t('Mic_off')}
    icon={controllersConfig.mic ? 'mic' : 'mic-off'}
<strong>    disabled
</strong>/>
</code></pre>

{% code overflow="wrap" %}
```tsx
const VideoConfController = ({ icon, active, secondary, disabled, small = true, ...props }: VideoConfControllerProps): ReactElement => {
	const id = useUniqueId();

	return (
		<IconButton
			small={small}
			icon={icon}
			id={id}
			info={active}
			disabled={disabled}
			secondary={secondary || active || disabled}
			{...props}
		/>
	);
};
```
{% endcode %}

3. **Avoid direct styles**

Refrain from applying direct styles to components. By avoiding inline styling, the code maintains a cleaner structure and promotes better separation of concerns, enhancing maintainability and readability.

```tsx
<VideoConfPopup>
	<VideoConfPopupHeader>
		<VideoConfPopupTitle text={t('Calling')} counter />
		<VideoConfPopupControllers>
			<Box display='flex' alignItems='center'>
				<VideoConfController
					width='50px'
					height='50px'
					active={controllersConfig.cam}
					title={controllersConfig.cam ? t('Cam_on') : t('Cam_off')}
					icon={controllersConfig.cam ? 'video' : 'video-off'}
					disabled
				/>
				<VideoConfController
					active={controllersConfig.mic}
					title={controllersConfig.mic ? t('Mic_on') : t('Mic_off')}
					icon={controllersConfig.mic ? 'mic' : 'mic-off'}
					disabled
				/>
			</Box>
		</VideoConfPopupControllers>
	</VideoConfPopupHeader>
</VideoConfPopup>

```

4. **Don't write CSS styles in JS files**

This approach separates your component's logic from styling, promoting better code organization and maintainability while avoiding inline CSS-in-JS styling.

Define your custom styling in an external CSS file:

```css
/* styles.css */
.customClass {
	border: 1px solid black;
	padding: 1.5rem;
}
```

Then, apply the class to your component:

```jsx
import './styles.css';

return (
    <VideoConfPopup>
        <VideoConfPopupHeader>
            <VideoConfPopupTitle text={t('Calling')} counter />
            <VideoConfPopupControllers>
                <VideoConfController
                    className="customClass"
                    active={controllersConfig.cam}
                    title={controllersConfig.cam ? t('Cam_on') : t('Cam_off')}
                    icon={controllersConfig.cam ? 'video' : 'video-off'}
                    disabled
                />
                <VideoConfController
                    active={controllersConfig.mic}
                    title={controllersConfig.mic ? t('Mic_on') : t('Mic_off')}
                    icon={controllersConfig.mic ? 'mic' : 'mic-off'}
                    disabled
                />
            </VideoConfPopupControllers>
        </VideoConfPopupHeader>
    </VideoConfPopup>
);
```

5. **Use the states of the component**

By using component states to conditionally render different complex components, you maintain a clear and organized structure in your code, enhancing readability and maintainability.\


```tsx
if (isReceiving) {
    return <IncomingPopup room={room} id={id} position={position} onClose={onClose} onMute={handleMute} onConfirm={handleConfirm}
}

if (isCalling) {
    return <OutgoingPopup room={room} id={id} onClose={onClose} 
}

return <StartCallPopup loading={starting} room={room} id={id} onClose={dismissOutgoing} onConfirm={handleStartCall} />
```

Each state should render the proper **Complex Component**:

```tsx
const OutgoingPopup = ({ room, onClose, id }: OutgoingPopupProps): ReactElement => {
	const t = useTranslation();
	const videoConfPreferences = useVideoConfPreferences();
	const { controllersConfig } = useVideoConfControllers();
	
	return (
		<VideoConfPopup>
			<VideoConfPopupHeader>
				<VideoConfPopupTitle text={t('Calling')} counter />
				<VideoConfPopupControllers>
					<VideoConfController
						active={controllersConfig.cam}
						title={controllersConfig.cam ? t('Cam_on') : t('Cam_off')}
						icon={controllersConfig.cam ? 'video' : 'video-off'}
						disabled
					/>
					<VideoConfController
						active={controllersConfig.mic}
						title={controllersConfig.mic ? t('Mic_on') : t('Mic_off')}
						icon={controllersConfig.mic ? 'mic' : 'mic-off'}
						disabled
					/>
				</VideoConfPopupControllers>
			</VideoConfPopupHeader>
		</VideoConfPopup>
	);
}
```

### Visual Components

**Visual components** are responsible for the appearance of a UI element. They define the element's style, layout, and other visual properties.

Adhering to guidelines in the Fuselage's componentization offers the value of modular, reusable, and maintainable UI components. This approach enables efficient development, ensures consistent behavior, and supports the evolution of solutions from specific contexts to broader applications. By encapsulating logic, avoiding direct styles, and leveraging API-driven customization, developers can create a streamlined and user-centered experience.
