---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

{% include base_path %}

## ChangeMakers Camp EMA

A signal-contingent **ecological momentary assessment (EMA)** protocol for children's screen-use
context, embedded in the six-week ChangeMakers Camp randomized trial at LSU
(IRB IRBAM-25-0015; PI Senlin Chen).

Instead of licensing a dedicated EMA platform, the study linked two systems the lab already
operated: the child-facing [**ProudMe iOS app**](https://proudme.org/#features)
([App Store](https://apps.apple.com/us/app/proudme-healthy-habits/id6772700786)) for
**push notification** delivery, and an institutionally licensed **Qualtrics survey** for data
capture.

<p align="center">
  <a href="{{ base_path }}/files/ChangeMakers-Camp-EMA-Summary.pdf">
    <img src="{{ base_path }}/images/proudme-ema-summary.png" width="560" alt="ChangeMakers Camp EMA implementation summary" />
  </a>
</p>

**Deployment.** 34 children ages 10 to 11 across two cohorts; 30 scheduled prompts per child over
three 3-day bursts in July 2026 (Camp Week 5, Camp Week 6, and post-test). Prompts were randomized
within 3-hour blocks between 8:00 a.m. and 8:00 p.m., with one reminder after 5 minutes and a
15-minute response window.

**Response pathway.** Four steps, not one tap:

1. **Signal scheduled**: prompt windows pre-specified by camp/remote/post-test day and time block
2. **ProudMe notification**: push prompt delivered to the child's study phone
3. **Grown-up check**: Apple's Kids Category policy required a parental gate (two-digit
   multiplication) before any external link
4. **Qualtrics EMA**: survey opened in the browser, with PID and prompt metadata passed through
   URL embedded fields

**What it measured.** Screen use immediately before the prompt; the behavioral context when the
child was not on a screen; screen type and device; social context (alone, or who else was present);
and physical location, with skip logic so follow-up items displayed only when relevant.

**Implementation takeaways.** The strongest technical result was the identifier chain: a dashboard
`PID` carried from ProudMe login through the Qualtrics URL into the export, so every matched record
joined to exactly one roster row. Block ID, prompt ID, and send-time fields supported prompt-level
reconciliation. Delivery, by contrast, depended on three per-child preconditions that were never
recorded for every child: app build version, iOS notification permission, and dashboard enrollment.
That contrast is the central lesson carried into the formative feasibility write-up.

[**Download the implementation summary (PDF)**]({{ base_path }}/files/ChangeMakers-Camp-EMA-Summary.pdf)
