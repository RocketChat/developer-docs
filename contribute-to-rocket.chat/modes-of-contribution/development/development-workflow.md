# Development Workflow

Building on from our [.](./ "mention") mode of contribution guide, this guide delves into the specifics of Rocket.Chat's development workflow. It's designed to help you navigate through issue prioritization, the pull request process, and more. Let's dive into the details of contributing effectively to Rocket.Chat.

### **1. Issue Assignment and Responsibility:**

* Start working on an issue you're assigned to. If you're not assigned to any issue, find the highest priority issue you can work on, assign it to yourself, and start working on it. Priority is given by milestones. You should always check issues in the current milestone, then short-term, middle-term, and long-term in that order.
* You are responsible for the issue you're assigned. If you can't complete it, communicate with your team, lead, or manager to have it reassigned or postponed.
* Once your code has been deployed in the release-candidate environment, verify that your changes work as intended. We have seen issues where bugs did not appear in development but showed in production due to merge issues.

### **2. Choosing Work:**

* Prioritize work with the highest priority based on the current milestone. The priority of items is defined under labels in the repository.
* Choose something that you're able to tackle and falls under your responsibility. Take a good look at our [labels](https://github.com/RocketChat/Rocket.Chat/labels) and see which ones apply to your position.

{% hint style="info" %}
To filter very precisely, you could filter all issues for:

* Milestone: Whichever is the current version
* Assignee: Unassigned
* Label: Your label of choice. For instance feat: api, feat: integration / plugin, feat: webrtc, subj: ui/ux, subj: security
* Sort by priority
{% endhint %}

* If you're unsure about what to work on, ask your team, lead, or manager.

### **3. Branching and Pull Requests:**

* Create or switch to a branch specific to the feature you are working on.
* You can create a Pull Request anytime during your development phase. Just make sure you add the label `stat: in progress` while the PR is not ready for merge and remember to remove the label when it is.
* When naming your Pull Request, start the name with one of the following tags for identifying changes:  **\[NEW]** for new features (eg. `[NEW] WhiteBoard integration`). **\[FIX]** for bug fixes. You should include the issue number(s) in parenthesis whenever possible. (eg. `[FIX] OTR timeout problems (#629, #2535)`). **\[BREAK]** for giving proper attention to changes that will break previous versions of Rocket.Chat (eg. `[BREAK] Change notification setting type from boolean to string`)

### **4. Adding changeset to your Pull Request**

A changeset is a piece of information about changes made in a branch or commit, that will be present in the changelog of the release.&#x20;

{% hint style="info" %}
#### To write **good** changesets:

* Changesets are intended for customers, so the language used should be appropriate for that audience. Avoid getting too technical in your explanations.
* Similarly, refrain from merely replicating the PR title in the changeset, as PR titles are designed for developers, not customers.
*   Should be written in the past tense, using a descriptive verb

    ❌`fix: Something I did`

    ✅`Fixed a problem where...` or `Added capability for users to...`
* Ensure your changesets are written in clear, grammatically correct English. This is crucial as changesets are processed automatically. Reviewers should bear this in mind when evaluating pull requests.
*   Should be small and concise

    ❌ `Once upon a time...`

    ✅ `Fixed problem caused by X`
* Feature branches should, in general, have one changeset on the main branch. Try to create this at the end of the development so it picks all the changes to the packages.
* While pull requests can contain multiple changesets, each with unique updates, it's recommended to avoid duplicating changesets that convey identical information.
* Since changesets are not for devs, `refactors` and `chore` tasks should generally not include one.
* `fix`, `regression` and `improve` should always have a changeset.
{% endhint %}

### **5. Getting your pull request reviewed, approved, and merged**:&#x20;

There are a few rules to get your pull request accepted:

* All checks have passed.
* Travis CI runs automatically when you push your pull request. If Travis fails, take a look at the reasons for failure. If it fails for no apparent reason, try running it again.
* You must sign the [Contributor License Agreement (CLA)](https://cla-assistant.io/RocketChat/Rocket.Chat).
* At least one team member must approve the Pull Request. If you don't know who to ask for approval, let your team, lead, or manager know you need one, and someone will be assigned as a reviewer.

### **6. Finishing a release branch**:&#x20;

When the state of the `release-candidate` branch is ready to become a real release, some actions need to be carried out. First, the release branch is merged into `master` since every commit on `master` is a new release by definition. Next, that commit on `master` must be tagged for easy future reference to this historical version. Finally, the changes made on the `release-candidate` branch need to be merged back into `develop`, so that future releases also contain these bug fixes. The release process is as follows:

```bash
$ git checkout master
Switched to branch 'master'
$ git merge --no-ff release-candidate
Merge made by recursive.
(Summary of changes)
$ git tag -a [version number]
```

To keep the changes made in the release branch, we need to merge those back into develop, though. In Git:

```bash
$ git checkout develop
Switched to branch 'develop'
$ git merge --no-ff release-candidate
Merge made by recursive.
(Summary of changes)
```

To create the new `release-candidate` based on `develop`:

```bash
$ git checkout release-candidate
Switched to branch 'release-candidate'
$ git merge --no-ff develop
Merge made by recursive.
(Summary of changes)
```

Every team member should strive to thoroughly test the `release-candidate` branch, especially regarding issues they have worked on. Any bug fixes applied to `release-candidate` should immediately be cherry-picked into `develop`.

You can learn more about our branching model from Vincent Driessen's article, '[A Successful Git Branching Model](http://nvie.com/posts/a-successful-git-branching-model/)'.

### **7. Hotfixes**:

Hotfix branches are very much like release branches in that they are also meant to prepare for a new production release, albeit unplanned. They arise from the necessity to act immediately upon an undesired state of a live production version. When a critical bug in a production version must be resolved directly, a hotfix branch may be branched off from the corresponding tag on the master branch that marks the production version.

Hotfix branches are created from the `master` branch:

```bash
$ git checkout -b hotfix-[current-version].[sub-version] master
Switched to a new branch "hotfix-X.X.X"
```

Then, fix the bug and commit the fix. Later, merge the bugfix into `master` and also into `release-candidate` (and `develop` if the bugfix cannot wait for the release branch to be finished).

```bash
$ git commit -m "Fixed severe production problem"
[hotfix-X.X.X abc12d3] Fixed severe production problem
5 files changed, 32 insertions(+), 17 deletions(-)

$ git checkout master
Switched to branch 'master'
$ git merge --no-ff hotfix-X.X.X
Merge made by recursive.
(Summary of changes)
$ git tag -a [current-version].[sub-version]

$ git checkout release-candidate
Switched to branch 'release-candidate'
$ git merge --no-ff hotfix-X.X.X
Merge made by recursive.
(Summary of changes)
```



### 8. GitHub issues handling

We utilize milestones and labels to manage issues asynchronously. The responsibility of scheduling of issues into milestones primarily falls on leads and product managers. The task of issue labeling is a collective effort, involving everyone.

Most issues will have labels for at least one of the following:

* Feat (`feat: accessibility`, `feat: embed`, `feat: livechat`, etc.)
* Subject (`subj: mobile`, `subj: security`, `subj: ui/ux`, etc.)
* Type (`type: bug`, `type: new feature`, `type: discussion`, etc.)

All labels are listed on the [labels page](https://github.com/RocketChat/Rocket.Chat/labels).

#### Labels of issues for community contributors

* Issues that are advantageous to our users and nice-to-haves, but for which we currently lack the resources or priority, are tagged as `contrib:`, indicating that contributions from the community are welcome to work on them.
* These issues are classified into `easy`, `intermediate`, and `experts needed` categories. This helps new contributors to select an issue to work on when they join the project, based on the perceived difficulty level of the task associated with the issue.

### 9. Bugs reporting

For information on bug reporting, please refer to [report-bugs.md](../report-bugs.md "mention")
