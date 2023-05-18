# Componentization

The components can be: `Simple` or `Complex` and `Visual` or `Logical`

The components can live on: `Application` or `Fuselage Library`

The components rules matrix

|                   | Fuselage Level | Application Level |
| ----------------- | -------------- | ----------------- |
| Simple & Visual   | ✅              | ❌                 |
| Complex & Visual  | ✅              | ✅                 |
| Simple & Logical  | ❌              | ❌                 |
| Complex & Logical | ❌              | ✅                 |

### Simple Components

This is the lowest level of your component, a unique part of an interface. A good example of this is the `Button` Component

#### Variation over styles

Instead of using style based props names e.g. Blue or Gray, uses names that suggest the variation of your component e.g Primary or Secondary

![](https://user-images.githubusercontent.com/27704687/186257526-a3bce55a-3eeb-4815-9bf0-569e79528f5f.png)

#### Do not use magic numbers or values

✅ Correct example, passing the `small` and `square` prop that will handle the size of the component

```tsx
<Button small square>
    <Icon name='circle-arrow-down' size='x24' />
</Button>
```

❌ Wrong example, using magic numbers to define the size of the component

```tsx
<Button height='50px' width='50px' square>
    <Icon name='circle-arrow-down' size='x24' />
</Button>
```

#### Prefer customization through CSS-vars

It's not appropriate using CSS random values, do prefer to use customization using CSS-vars

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

#### Every variation should be exposed and described in Storybook

It's important to expose each variation to allow developers or designers to check the existing possibilities.\
Also, it should have a description, if the variation, isn't self-explanatory

![Screen Shot 2022-08-23 at 17 31 17](https://user-images.githubusercontent.com/27704687/186259765-4ee6e5e1-da1f-439b-aaac-05683714f75f.png)

#### Unit tests for the all possible component behaviors

Guarantee that all the planned behaviors be covered by unit tests

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

#### Avoid Box Component

The usage of `Box` is recommended for Simple or Complex Components **mainly** (save the cases when we need to quickly prototype a component) on the Application Level as it's a wildcard component, for simple components, we suggest avoiding it and building the component using HTML tags

### Complex Components

A mix of simple components results in a complex component

#### Only visual, no logic

Handle just the user interface and left it prepared to receive the logic

![](https://user-images.githubusercontent.com/27704687/186262142-bb6a3354-d1f4-410d-bde9-6640bd7ccbcd.png)

#### Split the component in an easy to understanding way

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

#### Preferred get started using Storybook, allowing to keep the logic away

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

#### Child Components can't be used outside of the scope

❌ Wrong example on composing components

```tsx
export const MyComponent: ComponentStory<typeof VideoConfMessage> = () => (
    <Box display='flex'>
        <form>
            <VideoConfMessageAction>Call ended</VideoConfMessageAction>
        </form>
    </Box>
);
```

✅ Correct example of composing components

```tsx
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

#### HTML elements, Box, and Box props should be encapsulated

❌ Wrong example on composing components

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

✅ Correct example of composing components

{% code overflow="wrap" %}
```tsx
const VideoConfMessage = ({ ...props }): ReactElement => (
    <Box mbs='x4' maxWidth='345' borderWidth={2} borderColor='neutral-200' borderRadius='x4' {...props}  />
);
```
{% endcode %}

#### Offer hooks as helpers

In the example below the `useVideoConfControllers` was provided to control the state of the popup's controllers

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

#### Understanding the component and defining the scope (where it's going to live)

Usually, a new component is born based on the needing of the Product Design Team, and it's the responsibility of the front-end engineer to verify the real need of this new component. A new component generates a big effort, so it's highly recommended to validate with the product manager and the designers involved the possibility of using Complex Components as an MVP to validate the new idea and the user flow and only after, moving on to creating a new component on Fuselage Level.

> How do I know my component should be part of the Fuselage library?

A good example of this process is the `VerticalBar` the component which started as a Complex Component on the Application Level and now we're moving it to the Fuselage Level because more than one application can benefit from the component. E.g Rocket.Chat Application and Cloud Portal

### Logical Components

#### Use the child components, to compose a logical complex component

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

#### Hold the logic and state

_In development_

#### Customization through the variations

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

#### Avoid direct styles

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

#### Avoid CSS-in-JS

```tsx
const customClass = css`
	border: 1px solid black;
	padding: 1.5rem;
`;

return (
	<VideoConfPopup>
		<VideoConfPopupHeader>
			<VideoConfPopupTitle text={t('Calling')} counter />
			<VideoConfPopupControllers>
				<VideoConfController
					className={customClass}
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

#### Use the states of the component

```tsx
if (isReceiving) {
    return <IncomingPopup room={room} id={id} position={position} onClose={onClose} onMute={handleMute} onConfirm={handleConfirm}
}

if (isCalling) {
    return <OutgoingPopup room={room} id={id} onClose={onClose} 
}

return <StartCallPopup loading={starting} room={room} id={id} onClose={dismissOutgoing} onConfirm={handleStartCall} />
```

Each state should render the proper Complex Component

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
