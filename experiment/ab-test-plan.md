# A/B Test Plan: Homepage Headline

**Website:** Northwoods Snowmobile Guide  
**Page:** Homepage  
**Planned sample:** 100 trials (50 per version)  
**Expected completion:** November 24, 2026

## Element and versions

Test only the homepage's main headline. All other page content and presentation will remain identical.

- **A (control):** “Your Northern Wisconsin Snowmobile Guide”
- **B (variant):** “Find Snowmobile Trail, Safety & Destination Information for Northern Wisconsin”

Version A is the existing homepage: https://clarepiazza.github.io/snowmobile-guide/  
Version B will be published at: https://clarepiazza.github.io/snowmobile-guide/index-b.html. Version B will be excluded from the sitemap and marked noindex so it does not compete with Version A in search.

## Hypothesis and rationale

**Hypothesis:** AI visitors shown Version B will be more likely to choose to explore at least one additional page than visitors shown Version A.

Version B names the types of information available on the site—trails, safety, and destinations—so it may communicate the site's value more clearly than the general description in Version A and encourage further exploration.

## Visitor, model, and exact prompt

**Target visitor/persona:** An adult interested in snowmobiling in Northern Wisconsin who is seeking useful information about trails, safety, gear, or destinations.

**Model:** GPT-6 (ChatGPT, Free plan). Use the same model selection, account plan, and settings for every trial. Record the model label and visible settings for each trial. If GPT-6 is unavailable or the model, plan, or settings change, pause and document the issue; do not silently switch models.

Each trial will be run in a fresh conversation with no memory of earlier trials. The live homepage URL will be provided in the prompt in the same way for every trial; only the assigned A or B URL will differ.

**Exact prompt (replace only the URL):**

You are an adult planning a snowmobiling trip to Northern Wisconsin. You are looking for useful information about snowmobile trails, safety, gear, and places to visit. Review this website: [ASSIGNED VERSION URL].

Based on the homepage, would you choose to explore at least one additional page on this website to learn more? Answer "Yes" or "No," followed by one sentence explaining your decision.

**Trial-level documentation:** For every trial, save screenshots showing the selected model and submitted prompt, along with the complete AI response. Record the trial number, date, assigned version, model and visible settings, exact response, and outcome score in the results file. Retain all screenshots in the experiment repository, organized by trial number. If any model or setting information is not visible, document that limitation.

## Assignment and sample

Run 100 trials: 50 for A and 50 for B. Before collecting responses, generate a randomized sequence containing exactly 50 A assignments and 50 B assignments. Save that sequence in the experiment files and follow it in order. Each trial will use a separate fresh conversation. Use the same prompt, persona, model, settings, and live-URL presentation method throughout.

## Primary outcome and scoring

The one primary outcome is whether the visitor says they would explore at least one additional page.

- Unambiguous **Yes** = 1
- **No** = 0
- **Maybe**, unsure, conditional, unclear, or any response other than an unambiguous = 0

Save the exact response and its score for every trial. Do not omit or rewrite unexpected responses.

## Analysis and stopping rule

Calculate the Yes rate for A and B and the difference (B minus A). Compare the two proportions using a two-sided two-proportion test at significance level 0.05. The results support the directional hypothesis only if B has a higher Yes rate and the test gives p < 0.05. Otherwise, the experiment will not provide sufficient statistical support for the hypothesis.

Complete all 100 assigned trials before evaluating the primary outcome. Do not stop early or change the hypothesis based on interim results. Record dated notes for any errors, interruptions, or deviations.
