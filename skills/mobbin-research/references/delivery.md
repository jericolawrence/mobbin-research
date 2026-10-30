# Delivery and comparison demos

Use the format agreed in the initial interview. The defaults below limit the user's review burden without limiting search depth.

## What to show first

1. **4–5 visual references.** For each: app, inspected image or supported gallery, canonical source link, the relevant pattern, why it fits this domain, and its main tradeoff. Use fewer if evidence is weak; state why.
2. **A compact comparison.** Compare the patterns against the brief's success criteria and explain how they inform the demos. Avoid invented numeric scores or user-testing claims.
3. **3 playable demos.** Label distinct directions and explain what each experiment tests. Link or open the runnable artifact, not just its source code. Include the baseline for comparison when accessible.
4. **A recommendation.** Name the leading direction, the evidence supporting it, and the uncertainty most likely to change it. A recommendation is not a production plan or ticket list.
5. **The saved report.** Link the Markdown findings and state search coverage, the stop reason, and material gaps. Mention that additional references are available; do not dump them into chat unless requested.

Then begin the post-delivery grilling round. Ask only choices the evidence and demos leave unresolved.

## Demo procedure

- Put demo files in a separate research/prototype directory. Do not edit production interfaces to create a comparison.
- Reuse the same task, content, and starting state across variants so behavior is what the user compares. Vary the interaction pattern, not just a color or easing constant.
- Provide a clear way to trigger, reset, and repeat the interaction. For reversible interactions, demonstrate both entry and exit. For motion comparisons, expose replay and a slower playback mode; test the normal speed as the primary experience.
- Preserve the task's essential controls and states. For search entry, check focus, keyboard behavior, cancellation, and return to the original context. Choose equivalent domain checks for other tasks.
- Make controls keyboard/touch usable and honor reduced motion for motion demos. Distinguish platform behavior simulated in a browser from behavior tested on a native runtime.
- Label authored timing, easing, or gestures as proposals. If the baseline cannot be reproduced faithfully, explain the difference rather than presenting a guess as current behavior.
- Validate by running each demo and exercising its main task, reversal/reset, and relevant keyboard or gesture states. Record what ran and what could not be verified. Source that compiles is not proof that a demo plays correctly.

If a required native runtime or display capability is unavailable, disclose the limitation and ask which supported demo format to use. Do not silently downgrade a native-behavior experiment into a browser mockup or claim unrun demos were verified.

## Saved findings

Follow the project's research-note convention. If there is none, use `docs/research/<date>-<topic>.md` and keep demos and authorized source assets together in a neighboring topic directory. In a projectless session, use an accessible output directory and link it explicitly.

Keep one report with:

- The confirmed brief and success criteria.
- The shortlist, comparison, evidence classifications, and recommendation.
- Demo locations, the differences each tests, and validation results.
- A search ledger, deduplicated additional candidates, reject reasons, source URLs, and stop reason.
- Access limitations, unverified behavior, and questions for the next decision round.

The additional collection should be discoverable without another search. On a follow-up request for more, reveal the next relevant candidates and explain what they add; extend the search only to address missing coverage or a changed goal.

## Sample invocation

> /mobbin-research Research a smoother, more native-feeling transition for the conversation search button in my SwiftUI app. Right now tapping it switches abruptly into search. Investigate the relevant code and domain context, then grill me on the important unresolved decisions. Once we agree on the brief, show 4–5 strong Mobbin references and 3 playable demos, with a recommendation and saved research report. Grill me again about the direction before planning changes.
