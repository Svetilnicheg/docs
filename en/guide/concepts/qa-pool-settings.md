# Setting up quality control

Quality control lets you get more accurate responses and restrict access to tasks for cheating Tolokers. Quality control consists of rules. All rules work independently.

{% note warning %}

Quality control rules that you set in the [project](../../glossary.md#project-ru) are applied to all project [pools](../../glossary.md#pool-ru), so you can't change them in one pool.

{% endnote %}


To set up quality control:
1. Go to the pool editing page
1. If you already have a pool with the appropriate quality control settings, you can copy it along with the audience settings. To do this, go to {% if locale == "en-com" %}**Tolokers filter**{% endif %} and click {% if locale == "en-com" %}**Copy settings from...**{% endif %} and then {% if locale == "en-com" %}**Add Quality Control Rule**{% endif %}.
1. Under {% if locale == "en-com" %}**Quality Control**{% endif %}, choose the rules you want to use.
    If you aren't sure what quality control rules you need, select a quality control preset with default settings.
1. Make settings for the rules you added. Below is a list of rules with links to detailed information about the rule settings.
1. Save the pool.


## List of rules {#id_z4l_prs_2lb}

- **To keep track of how often Tolokers make mistakes:**
    - [Control tasks](goldenset.md): Use them to assign a [skill](../../glossary.md#skill-ru) to Tolokers based on their responses to control tasks and ban Tolokers who submit incorrect responses.
    - [Majority vote](mvote.md): Quality is based on matching the response from the majority of Tolokers who complete the same task.
    - [Results of checking](reviewing-assignments.md): Evaluate Tolokers based on the number of accepted and rejected responses.

- **To protect your project from robots and cheaters:**
    - [Fast responses](quick-answers.md): Control the minimum time that must be spent per [task suite](../../glossary.md#task-page-ru).
    - [Captcha](captcha.md): Show a captcha from time to time to make sure tasks aren't completed by robots.
    - [Skipped assignments](skipped-assignments.md): Restrict access to your pool tasks for Tolokers who [skip multiple assignments](pool_statistic-pool.md#skipped-tasks) in a row.

- **To attract a variety of Tolokers:**
    - [Earnings](income.md): Limit the amount each Toloker can earn in the [pool](../../glossary.md#pool-ru) per day.
    - [Submitted assignments](submitted-answers.md): Limit how many assignments each Toloker can submit in the pool per day.

- **To allow recompletion of certain assignments:**
    - [Recompletion of assignments from banned users](restore-task-overlap.md): Send [completed assignments](../../glossary.md#submitted-answers-ru) to other Tolokers to redo them if the Toloker was banned.
    - [Processing of rejected and accepted assignments](reassessment-after-accepting.md): Send rejected assignments to other Tolokers to redo them.



## What's next {#what_next}

- [Add tasks to the pool](pool.md)
- Learn more about how to set up a pool:
    - [Setting up pricing](dynamic-pricing.md).
    - [Dynamic overlap](dynamic-overlap.md).
    - Selective [majority vote](selective-mvote.md) control.
    - [Filters](filters.md).
    - [Speed/quality balance](adjust.md).
    - [Reviewed assignments](offline-accept.md).



## Troubleshooting {#troubleshooting}

#### Setting up quality control

#### How do I set quality control in a pool correctly?

The settings for [quality control](../../glossary.md#quality-control-ru) rules depend on the type of tasks. General recommendations:

- Always use one or more ways to control quality of answers.

- Counting [fast responses](quick-answers.md) makes sense for most tasks.

- If the Toloker has to choose between options (for example, by selecting checkboxes), check the answers using [majority vote](mvote.md) or [control tasks](goldenset.md).

- If the Toloker has to provide a response as a text or link or upload a photo, the best way to control quality is by [reviewing assignments](accept.md). You can outsource task acceptance to Tolokers. Create a task with a question (for example, "Is this phrase translated correctly?") and possible responses (for example, "yes"/"no"). Set up [overlap](dynamic-overlap.md) and [majority vote](mvote.md) check.

- If a task is more like an opinion poll (for example, choosing nice pictures from a set), [majority vote](../../glossary.md#majority-vote-ru) is not a good way to control quality. Make [control tasks](../../glossary.md#control-task-ru) with artificial examples where the choice is evident.


#### Should I create a skill for every pool?

It is better to use one [skill](../../glossary.md#skill-ru) in a project. You can choose the way to calculate the skill:

- Calculate the skill for each pool separately. The current skill value is the value of the skill in the pool the Toloker completed last. This option is convenient if:

    - The pools are intended for different groups of Tolokers (for example, there are filters by city or country).

    - Pools are started one by one and you don't want to take into account the responses in the previous pools to calculate the skill in the current pool.

    This calculation method is used by default when adding a quality control rule to a pool. For the control tasks block, leave the **Recent control task responses to use** field empty.

- Calculate skill based on all tasks in a project This option is good if the pools are small and you don't need to have skill calculated for each pool.

    This option is available only for skills on control tasks. To use it, fill in the **Recent control task responses to use** field in pool quality control rules.


#### Can I use a skill beyond a particular pool or project and apply it to other projects as well?

Yes, of course — you can use the same skill for different projects. But most often, a skill is intended for a specific project. If the Toloker completes a certain task well, this doesn't mean that they will complete other ones successfully. Another disadvantage is that if you filter by skills that were set long ago, you will artificially limit the number of available Tolokers.

#### I set up quality control, then I copied my user requirements. All my quality control settings were deleted and replaced with the copied settings. Is that normal?

Yes. When you copy the filter and quality control settings, the settings you previously added manually are overwritten. You should see a warning about this in the copy settings window.

#### Can one Toloker get access to two pools in the same project? Can I avoid that?

Yes, if they can access both pools, they can do both of them. To restrict access to subsequent tasks for a Toloker, use the [Completed tasks](submitted-answers.md) rule and select a ban at the project level.

#### Have I understood correctly that if I use `set the the skill value = 1` with the `percentage of accepted responses >= 75` and `10 recent values to use`, for every 8 correctly completed tasks out of 10 the Toloker is given 1 skill point?

No, this is incorrect. With these settings, each time a rule condition is met, the Toloker gets `skill = 1`. To change the skill value in the process of task review, you need a "multi-step" rule, which has multiple identical rules with different values of **Total reviewed responses**.

#### Is the time specified per task suite in the fast response settings?

Yes, the [fast response](quick-answers.md) settings specify the time per task suite.

#### How do I test users to determine which kinds of tasks they do better and assign them relevant tasks?

You can add a [training pool](train.md) to test your Tolokers. Based on the test results, assign skills to the Tolokers for the tasks they do best.

Then open your pools only to the Tolokers that have a certain skill: use [filters](filters.md) for this.

#### I want to create training and exam pools to match the entered text against a sample, and sometimes the matching fails. How do I implement this?

For a control or training assignment to be counted as correct, it must exactly match the control assignment. To do this, you need to normalize the response text using JavaScript: remove spaces, punctuation marks, special characters, and capital letters, and write the result in a separate output field. Now you can match the processed assignment text against your control text.

Another option for selecting Tolokers for a project of this type is assignment review (non-automatic acceptance).

#### I want to create an exam with three tasks. If a user does two out of three tasks correctly, they get the skill. So I try to use `3` in the **Recent control task responses to use** field, but I get an error that the value is too small. Can I get around this without increasing the number of tasks to five?

The **Recent control task responses to use** field is for the number of recent responses from the Toloker. If you use non-automatic acceptance for your task, then to set up your intended rule you need to specify `3` in **Total reviewed responses**.

#### I have two text versions that I want to show to my respondents: one version to half of the audience, and another version to the other half (like in A/B testing). Is this possible in Toloka, or do I need to create two separate projects?

If you pass texts to the input data, you can load 2 different tasks in the pool. In one task, pass Text 1 in the `INPUT: <input field name>` field, and in the other task, use this field to pass Text 2. But if the text is in the HTML block of the task template, you need to clone the project. To let a Toloker do only one task in your project, use the [Submitted responses](submitted-answers.md) rule. You can assign a skill or ban the Toloker after they submit one response.

#### Control tasks

#### How many control tasks do I need to add?

We recommend adding at least 1% of control tasks in the pool. And for small pools — 5-10%.

#### Why's that?

Each control task is shown to the Toloker only once. If you use smart mixing, you determine how many control tasks should be in a suite. If each suite contains one control task, then the maximum number of suites the Toloker can complete is equal to the number of control tasks in the pool. If you increase the number of control tasks in a suite, the number of suites available to the Toloker decreases by the same number.

There shouldn't be too few pages available. Otherwise:

- You won't be able to correctly evaluate the quality of the Toloker's responses.
- The Toloker won't be interested in completing such tasks because they'll spend a lot of time studying instructions but won't earn much.

#### Example

#### A large pool with 1% of control tasks (good)

There are 10,000 tasks in the pool, and 100 of them are control tasks (1%). Each suite contains 10 tasks, and 1 of them is a control task. Hence, a user can complete up to 100 suites.

#### A small pool with 1% control tasks (bad)

There are 100 tasks in the pool, and 1 of them is a control task (1%). Each suite contains 10 tasks, and 1 of them is a control task. Hence, each user can only complete 1 suite.

#### A small pool with 10% control tasks (good)

There are 100 tasks in the pool, and 10 of them are control tasks (10%). Each suite contains 10 tasks, and 1 of them is a control task. Hence, each user can complete up to 100 suites

If there are few control tasks in the open pool, [add new control tasks](../troubleshooting/pool-setup.md#add-gs).

#### What for

In a large pool with few control tasks, a situation might occur when users who have completed a lot of tasks in the project stop getting new task suites. This happens when the Toloker completes all control tasks in the pool.

{% note info %}

To filter out Tolokers, use the [Control tasks](control.md) quality control rule. To rank Tolokers by the quality of responses in control tasks, use a [skill](nav.md).

{% endnote %}


#### How are the correct responses to control questions counted?

The Control tasks rule starts working after the Toloker completes the number of control tasks you specified. If your pool contains both [training](../../glossary.md#training-task-ru) and control tasks, you can take into account the responses in both of them (the **Number of responses** parameter) or only in control tasks (the **Number of control responses** parameter).

As soon as the needed number of responses is collected, Toloka calculates the percentage of correct and incorrect responses and performs an action (assigns a skill, or blocks the Toloker in the pool or in the project). Then this percentage is updated as the tasks are completed by the Toloker. The number of the Toloker's recent responses that's used in the calculation is set in the **Recent control task responses to use** field. If you leave it empty, all the responses from the Toloker in the pool are counted.

#### Can I make my training or control tasks totally different from the general tasks?

Your [training](train.md) and control tasks have the same project specification. However, you can create a separate project with the tasks and assign a skill based on user responses. Then you can admit Tolokers to the main project based on their skill.

#### Isn't the exam a regular pool that I pay for? How does it differ from a regular pool?

An exam pool contains only control tasks. It's usually small and used for checking how well users learned to do your tasks after they read the instructions and completed the [training](additionals-q.md#selection). Unlike your main pool, you already know the correct responses for every task in this pool. You can set the price to zero.

Based on the results of responses to control tasks, you can assign a skill to the Tolokers and then specify it in the main pool as a filter. For example, `MySkill = 80 or = Is missing`. You don't have to create an exam. For simple tasks, the training pool provides enough practice, but many requesters also use exams.

#### How do I set up an exam so that different people can take it without running out of tasks?

When you load tasks, use smart mixing. In this case, you'll have infinite overlap in your exam.

However, this poses the risk that you might spend a lot of money on the exam. You might want to open this pool only when the main pool opens, and close it when labeling of the main pool ends.

#### If I upload tasks using smart mixing, does it mean that the same file should contain both the control tasks and general tasks, or can I upload them separately?

Smart mixing is set up when you upload tasks to the pool. After creating a pool, click **Upload** and select the method for generating task suites. You can upload them using separate files or one file, arranging them in any order.

#### Can I create two active training pools, one for practice and the other for admitting users to the main pool? In other words, one pool is for users to practice and the other pool tests them.

Yes, you can do that. In this case, create the first pool based on the [training pool](../../glossary.md#training-pool-ru) and the exam pool based on your main pool. If a pool contains only control and/or training tasks, the price can be set to zero.

In the exam pool, you can create a skill reflecting the exam result and granting admission to the main pool. For example, `if the number of responses is ≥ 10, set the skill value in the <exam skill> as % of correct responses`. In your exam pool user requirements, specify: `<exam skill> < 80 or = Is missing>`. In the main pool, set up a filter: `<exam skill> >= 80 and (<main skill> >= 70 or = Is missing)`. You can choose the skill values depending on how well the Tolokers handle your task.

#### I created a training pool with one task containing a hint. The Toloker fails to complete the task on the first attempt, but finally succeeds. The Toloker gets the skill `0`. How do I grant to the Toloker access to my tasks? The minimum required level that you can set is `10`.

Technically, if you have only one task in your training pool, you don't have this option. The skill will be either `0` or `100`. We recommend that you add several tasks, or at least 2 so that the Toloker will practice on the first task and will be able to do the second task correctly. In this case, you can admit users to your main pool starting from the skill value of `50`.

You can also create a training pool based on the main pool. Assign a skill using the [Control tasks](goldenset.md) rule: in this case, you can admit users with any skill level to your main pool, even if the value is zero. But we don't advise giving tasks to people who failed training.

#### In the section about control questions, does "Number of control responses" mean the total number of responses to control questions (including incorrect responses) or the number of correct responses to my control questions?

This is the total number of responses to the control questions.

#### Can I use non-automatic acceptance in the training pool?

No. But you can create a pool of the **Training** type based on your main pool and enable non-automatic acceptance there.

#### Can the Tolokers see which questions are control tasks?

No, they can't.

#### When I export a project from the Sandbox, the task files are not exported. Is this how it's supposed to work? I suddenly lost the markup of the control tasks that I created in the sandbox.

The tasks themselves are not exported, only the project configuration and the settings of the selected pool. However, you can download your marked up tasks from the **Sandbox** pool and import them to the pool you created. To download the control tasks only (if you marked them up in the interface), go to **Mark up**, then click **Control tasks** and **Download**.

#### Ban

#### Can I disable tasks for Tolokers who do a poor job on tasks?

You can deny access to the pool if the Toloker's responses are [too fast](quick-answers.md), if they don't match the [majority vote](mvote.md), or if the Toloker makes too many mistakes in [control tasks](goldenset.md). Tasks completed by such Tolokers can be [given to other Tolokers](restore-task-overlap.md).

#### I set up a rule to ban users after the first incorrect captcha. This is to eliminate any bots. Is this too strict? What rule do most projects use?

Indeed, this rule is probably too strict. Even the most careful user can make a mistake, so you probably want to relax the rule. Besides the requester-specific bans, we have system processes that ban users who regularly fail captcha checks in Toloka.

#### If a cheating Toloker gives a lot of incorrect responses, and the system eventually bans them for errors in control tasks, do I have to pay for the bad responses anyway?

If the Toloker already got paid for the tasks, the money can't be refunded to you.

#### If I ban users from my project so that everyone can complete a maximum of one task, are the Tolokers notified of the ban?

No, the Tolokers are unaware of the ban.

#### If I ban a Toloker for doing my tasks too fast, will all their responses be deleted and given to other Tolokers for labeling?

No. The responses of these Tolokers aren't automatically excluded from the final results file.

But you can do it yourself if you want. When downloading the results, select the option **Exclude assignments by banned users** to delete the responses of Tolokers who were banned at the moment of downloading. You can also forward all the assignments from banned users to other Tolokers using the [Re-completion of assignments from banned users](restore-task-overlap.md) rule.

#### How do I classify users as good Tolokers and poor Tolokers as they complete tasks, and ban the poor Tolokers?

You can create a task pool for all your Tolokers and create Toloker skills in it. In this case, you can open your tasks only to the Tolokers with the necessary skills.

#### Captcha

#### Can I control the frequency of showing captchas to the Tolokers? Some Tolokers get a bit demotivated by that.

The frequency of issuing [captchas](captcha.md) is set up in the pool.
#### No
Don't show captchas.
#### Low
Show a captcha after every 20 assignments.
#### Average/High
Show a captcha after every 10 assignments.

#### Can I get more details on the best practices for using captchas? For which projects is it better to use captchas and how often?

[Captcha](captcha.md) is usually used in simple projects with automatic acceptance, like classification, categorization, or information search. These are cases where there are few response options and users don't need to upload files or write texts. It helps you filter out bots and sloppy Tolokers.

The frequency of issuing captchas is configured in the pool.
#### No
Don't show captchas.
#### Low
Show a captcha after every 20 assignments.
#### Average/High
Show a captcha after every 10 assignments.

#### I found the following terms related to captcha in Help: "Percentage of correct responses" and "Percentage of incorrect responses". Are they determined from the control sample?

The percentage of correct responses is based on the total number of captchas processed by the Toloker within the "range" specified in the **Recent control task responses to use** field. If the value is empty, the percentage is calculated using all the captchas that are shown for the tasks in the pool which uses the captcha rule.

#### Majority vote

#### The pool has an overlap and majority vote set up, but some fraudulent user opens the task suites, does nothing, and submits empty assignments. Could this cheater get more tasks from the pool before the results of other Tolokers are known? Could a user quickly click through a lot of task suites before the majority vote is accumulated to ban the cheater?

Yes, unfortunately, this can happen. This is why we recommend that you offer a training task or exam before the general task. In this case, only those people who showed good performance at the previous stage are selected for the main pool.

#### My task uses a form with multiple fields. When there is an overlap and "Majority vote" is used for quality control, is each field taken into account, or if one field mismatches the majority vote, are the task results considered incorrect?

All responses to the task are taken into account. If one response differs from the majority vote, the whole task is counted as mismatching the responses of other Tolokers.

#### What output format do I use for the review results to filter out mismatching users based on the "Majority vote"?

To perform actions with users (assign a skill or ban them) based on the majority vote, add a relevant [rule](mvote.md) to the pool.

Don't forget to enable **Keep task order** in the pool parameters. Majority vote is used in the projects with preset options (radio buttons or checkboxes). This rule won't apply to the text entry or file upload fields.

#### Speed of task completion

#### Why has the speed of pool completion dropped?

Possible reasons:
- You've stopped the [main pool](../../glossary.md#training-pool-ru). This could limit the number of Tolokers with access to the pool. Start the training pool again. There will be more Tolokers who can access the tasks.

- The filters you set are too strict. For example, a strong restriction on a certain skill that most users don't have.
- Too many users are banned. Ease the quality control rules.

#### How can I speed up the pool completion?

- To motivate Tolokers, assign a [public skill](nav-create.md#public) and use [dynamic pricing](dynamic-pricing.md).
- Try to [increase the project rating](project_rating_stat.md), so that your task is higher in the list of tasks for Tolokers.
- Adjust the [quality-speed ratio](adjust.md).
- Set a higher [priority](pool_poolparams.md#priority) for the pool among other project pools.


{% include [contact-support](../_includes/contact-support-help.md) %}