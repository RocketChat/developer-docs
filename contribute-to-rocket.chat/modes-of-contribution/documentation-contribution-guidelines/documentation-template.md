# Documentation Template

Rocket.Chat is a platform that values the accuracy and relevance of its documentation. This is crucial in ensuring that users and developers can effectively utilize and contribute to the platform. The process of updating the documentation is a collaborative effort that involves both the contributors and the documentation team. This guide provides a template and instructions on how to create a draft for the documentation when a pull request is made that could potentially alter existing documentation.

If you've made a pull request that you think could impact the existing documentation, this template is here to assist you in formulating the necessary modifications. Start by confirming if the feature you're enhancing is already covered in the existing documentation, which can be found at [https://docs.rocket.chat/](https://docs.rocket.chat/).

To put forward a draft, initiate a pull request from a branch in the repository and tag it as 'draft'. Subsequently, the documentation team will revise it to ensure it meets the documentation guidelines.

The draft's role is to equip the documentation team with the essential information to develop appropriate documentation for the updated feature. It's important to keep in mind that any modifications to a feature need to be mirrored in the documentation to avoid it becoming outdated or inaccurate.

Bear in mind that the template is flexible and doesn't always have to be adhered to strictly. If a certain field is not relevant, you can simply label it as "N/A".

Moreover, for smaller changes, it may be more efficient to create a pull request and directly update the documentation instead of creating a draft. So, feel free to directly make a pull request to revise the documentation when it seems suitable.

<details>

<summary>New Feature Template</summary>

```
# FEATURE NAME

**Added in version:** <!-- The version that feature was implemented -->

**Type of feature:** <!-- What type is the feature being created. E.g. API, User Feature, Admin Feature, Development Feature, etc... -->

**Involved settings:** <!-- Does this features adds or changes any setting? Which ones? What do they do? -->

**Description:** <!-- What does this feature do? -->

**How to use this feature:** <!-- How can this feature be used? -->
```

</details>

<details>

<summary>Feature Change Template</summary>

```
# FEATURE NAME

**Changed in version:** <!-- The version that feature was changed -->

**Link to original documentation:**

**Link to pull request:**

**What was changed:** <!-- What have change in the feature? -->

**Has the way to use the feature changed?:** <!-- To use that feature, will the user have to do something different than before? -->
```

</details>

<details>

<summary>Issue Template</summary>

```markdown
# Prerequisites

Please answer the following questions before opening an issue.

- [ ] I checked to make sure that this issue has not already been filed
- [ ] This issue concerns the developer's docs

> This template can be used to report
>
> - [Existing Docs issues](#existing-docs)
>
> - [New Docs request](#new-docs-request)
>
> **Clear out any irrelevant section**

## Existing Docs

### Expected Behavior

Please describe the behavior you are expecting

### Current Behavior

What is the current behavior?

### Steps to Reproduce

Please provide detailed steps for reproducing the issue.

1. step 1
2. step 2
3. you get it...

## New Docs Request

### Details

Please provide your details and description here.
> Add any information if you have to help develop the docs

## Extras

Please include any relevant information or images
```

</details>

Keeping the Rocket.Chat documentation up-to-date is a shared responsibility that requires the active participation of all contributors. By following the provided template and guidelines, contributors can effectively communicate changes and ensure that the documentation remains a reliable resource for all users. Remember, the goal is to maintain clarity and accuracy in the documentation, and your contributions play a vital role in achieving this.

{% hint style="info" %}
For a comprehensive guide on contributing to Rocket.Chat documentation, visit [.](./ "mention")and [markdown-style-guide.md](markdown-style-guide.md "mention")
{% endhint %}
