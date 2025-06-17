---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Feature Flags
# titleTemplate for the webpage, `%s` will be replaced by the slides deck's title
titleTemplate: "%s - Feature Flags"
info: |
  ## Feature Flags
# enable presenter mode, can be boolean, 'dev' or 'build'
presenter: "dev"
# download: true
# exportFilename: 'feature-flags'
highlighter: shiki
lineNumbers: true
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# take snapshot for each slide in the overview
overviewSnapshots: true
---

# Feature Flags

<!--
Hello everyone
On this opportunity, we will discuss "Feature Flags"
Hopefully, we can ...
-->

---
transition: fade-out
---

# Table of Contents

<Toc :style="{ columnCount: 2, columnGap: '5rem', height: '100%' }" />

<!--
As we all can see the Table of Contents,
There are few topics that we are gonna discuss,
First... *read first content to the end*
Last but not least... *read last content*
-->

---
transition: slide-left
layout: quote
---

# Moving Fast Without Breaking Things

No matter what industry you’re in, the pace of change keeps going up. 

To respond to all this change, we need to be able to make quick decisions, experiment, and adapt. 
Surely accelerating the pace of change means accepting a trade-off in terms of risk for bugs and errors slipping past QA, 
higher risk for deployment incidents, 
higher risk for security vulnerabilities. 
***“move fast and break things”*** as the saying goes.

Fortunately, that’s not necessarily the case. 
Over the last couple of decades, leading software organisations have demonstrated that accelerating the rate of change can actually reduce risk. 
It turns out that, when you use the right practices, you can ***“move fast with safety, deploy confidently, and migrate painlessly”***.

The obvious question is, what are these organisations doing that allows them to accelerate their pace of software delivery while still maintaining quality and stability? 
In large part, we can say that their success lies in a set of practices that accelerate the feedback loop between code being written and code being deployed.
A set of practices often referred to as ***Continuous Delivery***.

<!--
-->

---
transition: slide-left
layout: center
---

# Continuous Delivery

<img src="/cd.png" alt="Continuous Delivery" class="object-cover h-80" />

<!--
This cluster of techniques works together to achieve an interconnected set of principles:
- Reduce manual work in testing and deployment activities
- Work in small batches
- Keep codebase in a deployable state
- Architect systems for decoupled deployments
- Make frequent deployments to production

Organisations that focus on these Continuous Delivery practices are able to move faster than their competitors, while still maintaining safety and quality.

One practice that is used within these high-performing organisations is feature flagging.
-->

---
transition: slide-left
---

# What is Feature Flags?

Feature flags are a technique that allows teams to enable, disable or change the behavior of certain features or code paths in a product or service, without modifying the source code.

Feature flagging facilitates a core practice of Continuous Delivery: ***“separating deployment from release”***.

If a team wants to work in small batches and make frequent deployments to production, 
they are confronted with a challenge: 
what to do with work that doesn’t fit into one of those small batches? 

Let’s say the team doesn’t want to accumulate more than a week’s worth of code changes without a production deployment.
What do they do if they have a feature which is going to take two weeks to implement?

The answer is that they incrementally merge and deploy their changes all the way to production, 
despite it still being a work-in-progress. 
That’s ok though, because the changes are deployed as latent code, inactivated behind a feature flag. 

Then, once the feature is fully implemented (and tested) the feature flag is flipped on and the feature is released. 
This is what it means when we say deployment is separated from release: ***“the implementation of the feature is deployed incrementally, but the feature is only released when ready”***.

<!--
-->

---
transition: slide-up
layout: center
---

# Best Practices

---
transition: slide-up
layout: center
---

# 1. Clean up your feature flags

<br >

The best way to get the most out of feature flags is to clean them up after they’ve served their purpose.

Create a built-in process for flag archiving, making this a regular part of your engineers’ workflows,
just as important as reviewing pull requests or clearing issues in your issue tracker.

This will help manage tech debt and save your team time and messiness down the road.

Understand the difference between long-lived and short-lived flags and when to use them.

<!--
Short-lived flags are temporary flags used to control the rollout of new features, typically removed after the feature is fully released.

Short-lived h characteristics:
- Short lifespan (days or weeks)
- Are used to test new features, roll out changes to a small subset of users.
- Should be removed after the feature is fully released or it will become a tech debt.

Short-lived flags examples:
- New component rollout (new button component)
- API integration (new payment provider)
- Performace optimization (new data fetching strategy)
- New feature launch (new dark mode)

Long-lived flags are permanent flags used for operational control, A/B testing, or configuration management.

Long-lived characteristics:
- Long lifespan (months or years)
- Are used to control the behavior of a feature over time.
- Should be removed only if the feature is no longer needed.

Long-lived flags examples:
- A/B testing and experimentation (new dashboard layout/flow for conversion rate optimization test)
- User tier or permission-based features (advanced analytics for premium users)
- Regional or market-specific features (cookie banner for EU users)
- Operational kill switch (disable feature in case of emergency)
-->

---
transition: slide-up
layout: center
---

# 2. Design features around flags

<br >

Feature flag deployment should be planned early on in the software development process. 

If flags are simply layered in as an afterthought, they won’t be as effective. 
Whenever you start work on a new feature, think about how you can put it behind a feature flag. 
The possibilities of feature flags are endless, which makes it even more important to define a flag’s scope.

Start by defining exactly what each flag will do when:
- Disabled/enabled
- There’s a remote configuration value

Additionally, think about the rollout plan. 
Will you roll the feature out all at once, to segments, or to individuals?

<!--
-->

---
transition: slide-up
layout: center
---

# 3. Make flags as small as possible

<br >

Multitasking is great, but not when it comes to feature flags. 

Keep your feature flag scope specific. 

Start small—on/off flags are the simplest way to get started. 

When you’re comfortable with this, you can introduce more advanced capabilities.

<!--
-->

---
transition: slide-up
layout: center
---

# 4. Flags shouldn't replace business logic

<br >

Feature flag values shouldn’t be used as a replacement for business logic. 
If you create a situation where flags are interpreting code with branches that interpret rules, it becomes very easy to make a mistake.

Feature flag software is not an integrated development environment. 
If you treat it like one, you’ll lose a lot of the benefits of just writing code and being able to test it properly. 

For instance, you shouldn’t use feature flags for access control. 
If you feel that you’re using your feature flags to guard your data and segregate between different types of users, you should probably use business logic instead.

<!--
-->

---
transition: slide-left
layout: center
---

# 5. Create a naming convention

<br >

Having a well-defined naming convention is important for two reasons: 

1. Better team collaboration: users will understand what happens when a flag is turned on/off from its name alone.
2. It will remove the burden of decision every time you introduce a new flag and have to name it. 

<!--
-->

---
transition: slide-left
layout: center
---

# OpenFeature

<img src="https://repository-images.githubusercontent.com/837408076/c75a70a7-aad4-4a0a-b09c-10fb8aca6062" alt="OpenFeature" class="object-cover h-80" />

<!--
Because feature flags live deep in your codebase, it’s important to introduce them in the right way, 
avoiding locking you into specific vendors.

Your development teams write code against one consistent unified API, 
while your organisation maintains the freedom to use any provider.

Beside that, we can also use common terminology through a standardised glossary that aligns communication regardless of the tool or vendor.

OpenFeature is the answer to all these problems.
-->

---
transition: slide-left
layout: center
---

# OpenFeature

Demo

<!--
-->

---
layout: center
class: text-center
---

# Thank You 🙏

<PoweredBySlidev />

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/rifandani/feature-flags-slide" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl icon-btn !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>
