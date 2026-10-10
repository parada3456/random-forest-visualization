# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

Single-file static HTML/CSS/JS (`index.html`), no build step, no backend. Confirmed binding constraint: stay self-contained and statically hostable (e.g. GitHub Pages). Fonts load from Google Fonts.

## Users

Students learning machine learning, building intuition for how a random forest works. They arrive curious or confused about why averaging many overfit trees yields a stable predictor, and they learn by manipulating data and parameters and watching the result.

## Product Purpose

Random Forest Lab is an interactive visualization ("Random Forest, Step by Step") that shows how a random forest is built and why it works: bootstrap resampling of the data, random feature subsets at each split, individual decision trees, and voting/averaging into one predictor. It is a course project (a data-analysis class deliverable), so success means a student or grader can understand each mechanism by interacting with it, and the project presents well when shown or assessed.

## Positioning

Not a static diagram or a library demo: the learner builds the dataset themselves on a data canvas, tunes hyperparameters, and watches trees grow, the model state evolve and the error curve respond, with inline explanations (tooltips, collapsible "explain" toggles) of each step.

## Operating Context

Opened in a browser, on its own page. Workspace has a Data Canvas, Hyperparameters & Controls, Model State and Error Curve panels. Used in a study or classroom/presentation setting.

## Capabilities and Constraints

- Interactive data canvas with pan (infinite pan was an open item in early commits), class points, and a convex-hull view.
- Hyperparameters and controls, per-tree view with node-level Gini and split-threshold explanations, model state, and error curve.
- Runs entirely client-side; no server, accounts or persistence.
- Terminology to keep consistent: bootstrap sample, random feature subset, Gini impurity, leaf/internal node, vote.

## Brand Commitments

Existing name: "Random Forest Lab", with the page title "Random Forest, Step by Step" and the eyebrow "Interactive Machine Learning Visualization". No external brand, logo or style guide exists.

## Evidence on Hand

No testimonials, user data, benchmarks or external assets. Do not fabricate any. The README is a stub.

## Product Principles

1. Teach the mechanism, not just the result: every visual should map to a step in how the forest is built.
2. Learning by manipulation: the learner's own data and parameter changes drive what they see.
3. Explanations live next to what they explain, optional but always reachable.
4. Stay self-contained and static: no build, no backend, easy to host and submit.
5. Clear enough to be understood on a projector or in a grading review.

## Accessibility & Inclusion

No specific standard was established. Known gap from the detector: several text/background pairs fall below WCAG AA contrast (e.g. `#ab9ff4` on `#f4f3fd`, `#8a8778` on `#22221b` at 4.4:1). Treat WCAG AA as the working target for future work (not yet user-confirmed).
