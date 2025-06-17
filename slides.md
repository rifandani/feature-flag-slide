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

# What is Feature Flags?

No matter what industry you’re in, the pace of change keeps ratcheting up. 

To respond to all this change, we need to
be able to make quick decisions, experiment, and adapt. And given
the increasingly digital nature of every enterprise,
this naturally leads to higher and higher expectations
around the pace of software delivery.

But while expectations around the pace of software
delivery are increasing, expectations around
quality, security, and compliance remain the same,
particularly for larger enterprises operating in higher
regulatory environments.

On the face of it, this appears to be an unresolvable conflict. Surely accelerating the pace of change means
accepting a trade-off in terms of risk—higher risk
for bugs and errors slipping past QA, higher risk for
deployment incidents, higher risk for security vulnerabilities. “Move fast and break things”, as the saying
goes.

Happily, that’s not necessarily the case. Over the last
couple of decades, leading software organisations
have demonstrated that accelerating the rate of
change can actually reduce risk. It turns out that,
when you use the right practices, you can “move fast,
with safety”.

This claim—that a higher pace of software throughput
can lead to greater stability—may provoke some
healthy scepticism from yourself or your peers. It
certainly sounds a little counterintuitive. However,
this idea is backed up by solid empirical research, as
detailed by Dr. Nicole Forsgren and her DORA team
in their book Accelerate. This research group applied
statistical modelling techniques to data from over
23,000 survey responses, collected over the course
of multiple years, to try and understand the practices
that organisations around the world use to build
software, and how well those practices work.

One of the most interesting findings from this wideranging group was the correlation between a higher
pace of software throughput and higher levels of
stability and quality. It’s also worth noting that their
findings didn’t seem to be strongly affected by the
size or type of organisation—big or small, regulated
or not, the same correlations were evident.

The most exciting part is that the DORA team didn’t
stop at just looking at these performance metrics;
they also looked at the practices these different
organisations were using. They identified a specific
group of “high performer” organisations who were
differentiated on a key set of software delivery
metrics, and most importantly they were able to lay
out a set of software delivery practices that these
high-performing organisations used to achieve speed
with safety. 



<!--
-->

---
transition: slide-left
layout: quote
---

when you use the right practices, you can move fast with safety, deploy confidently, and migrate painlessly.

<!--
-->

---
transition: slide-left
---

# Continuous Delivery

<!--
-->

---
transition: slide-left
---

# OpenFeature

<img src="https://repository-images.githubusercontent.com/837408076/c75a70a7-aad4-4a0a-b09c-10fb8aca6062" alt="OpenFeature" class="object-cover h-80" />

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
