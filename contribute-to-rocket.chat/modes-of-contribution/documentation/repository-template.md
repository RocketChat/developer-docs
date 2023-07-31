# Repository Template

Here are the various templates for the documentation repository.

<details>

<summary>New Feature Template</summary>

If you have created a pull request creating a new feature please use this template to create a draft of the documentation.

To submit a draft, create a pull request (make sure you are doing it from a branch in the repository) and tag it as 'draft', after that the documentation team will edit it to suit the documentation standard.

The draft serves to give information to the documentation team so they can create the appropriate documentation for that feature.

Please try to be very detailed when writing about the feature, this will help create better documentation.

_Note: the template is not absolute, and in some cases, it might not make sense to follow the template by the letter. If a field can't be answered you can leave it as "N/A"_

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

If you created a pull request and believe that it could change something already documented, use this template to create a draft for the documentation.

Firstly, check if the feature you are working on is already documented by searching the existing docs at [https://docs.rocket.chat/](https://docs.rocket.chat/).

To submit a draft, create a pull request (make sure you are doing it from a branch in the repository) and tag it as 'draft', after that the documentation team will edit it to suit the documentation standard.

The draft serves to give information to the documentation team so they can create the appropriate documentation for that feature.

When a feature is changed, it's very important to update the documentation, the lack of this custom can lead to outdated and invalid documentation quickly.

_Note 1: the template is not absolute, and in some cases, it might not make sense to follow the template by the letter. If a field can't be answered you can leave it as "N/A"_

_Note 2: sometimes creating a pull request and doing the fix to the docs can be faster than creating a draft (especially in small changes), so don't be afraid to create a pull request directly to change the docs._

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

{% hint style="info" %}
For a comprehensive guide on contributing to Rocket.Chat documentation, visit [.](./ "mention")and [markdown-style-guide.md](markdown-style-guide.md "mention")
{% endhint %}
