# Random Forest Lab

**Random Forest, Step by Step** is an interactive, single-file web app that teaches how a random forest works, one tree at a time. You draw your own data, tune the hyperparameters, and watch the forest grow.

Live demo: https://parada3456.github.io/random-forest-visualization/ (after enabling GitHub Pages, see below)

## The idea

A random forest grows many decision trees, each on a **bootstrap sample** of the data (random draw with replacement), and lets every split consider only a **random subset of features**. Each tree on its own overfits, but averaging their votes gives one stable predictor.

- **Classification:** majority vote of the trees; split quality is measured with Gini impurity.
- **Regression:** mean of the trees' predictions; error is measured as RMSE.
- **OOB (out-of-bag) error:** each tree is scored on the points it never saw, a free validation set.

## Layout

| Area | What it does |
|---|---|
| Data Canvas (top left) | Spray points with a brush (size and density), erase, pan and zoom, undo, exact-point entry, or generate a dataset (Blobs, Moons, Circles, XOR, Spiral; Sine, Linear, Quadratic, Step, Wave for regression) |
| Hyperparameters & Controls (bottom left) | Number of trees, bootstrap size, random feature subset, max depth, min samples to split. **Step-by-step** grows one tree; **Play until Convergence** keeps growing until OOB error stays flat for 5 trees |
| Model State (top right) | Tree Detail (structure, Gini and thresholds), bootstrap weights map, Forest Overview with the final vote or average |
| Error Curve (bottom right) | OOB and training error (RMSE in regression) after each tree |

The Data Canvas shows the decision boundary (classification) or the prediction curve (regression) and updates after every tree. Switch between **Classification** and **Regression** in the header. The **How to use** button starts a guided tour.

## Versions

`main` and the live demo always show the **2-feature** version. The other versions are kept as tags; check one out (or download it from its tag page) to open it locally.

| Version | Features | Views | Where |
|---|---|---|---|
| [`v1.1.0`](https://github.com/parada3456/random-forest-visualization/tree/v1.1.0) | Always 2 (x, y), not changeable | 2D | `main`, live demo |
| [`v1.0.0`](https://github.com/parada3456/random-forest-visualization/tree/v1.0.0) | 2 to 6 (extra features are random noise) | 2D, on x and y only | tag |
| [`v1.2.0`](https://github.com/parada3456/random-forest-visualization/tree/v1.2.0) | 2 to 6 | 2D or 3D, with a choice of which 2 or 3 features to plot; the decision boundary is shown in both | tag, branch `feature/3d-multifeature` |

```bash
git checkout v1.2.0   # or v1.0.0 / v1.1.0, then open index.html
```

## Run locally

No build step or dependencies. Open `index.html` in a browser.

## Deploy to GitHub Pages

1. Push the repository to GitHub.
2. Go to Settings → Pages.
3. Under Source, choose the `main` branch and the `/ (root)` folder, then save.

Everything (HTML, CSS, JavaScript and fonts) lives in `index.html`, so no other files are needed.

## Team

CE KMITL

- 66010575 พิมพ์สิริน สุวรรณบุตร
- 66010751 วรินทร ลู่โรจน์เรือง
- 66010752 วรินธร หวังประเสริฐกุล
- 66010933 อาริยา อังศุวัฒนา
- 66011452 ภาราดา โพยนอก
