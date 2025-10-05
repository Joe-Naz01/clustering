# Unsupervised Clustering — K-Means, Scaling & Cross-Checks

**Problem.** Group similar items without labels and interpret the groupings for real-world insight.

**Data.**
- Wheat seeds (Kama, Rosa, Canadian) — geometric measurements.
- Fish measurements — numeric features requiring scaling.
- Stocks (daily price moves, 2010–2015, Yahoo! Finance) — patterns in co-movement.

**Approach.**
- Ran **K-Means** with elbow analysis (inertia) to pick k.
- Used **StandardScaler/Normalizer**; compared raw vs scaled clustering.
- Built **pipelines** (impute → scale → KMeans) for clean workflows.
- For seeds: cross-tabulated clusters vs known varieties to sanity-check separation.
- For stocks: normalized returns to reveal co-movement clusters.

**Results (qualitative).**
- Elbow suggested k≈3 on seeds; clusters aligned with grain varieties.
- Scaling was critical for fish data—improved separation and stability.
- Stock clusters revealed companies with similar movement profiles.

**What I Learned.**
- Why scaling can make/break distance-based clustering.
- How elbow plots guide k, and how cross-tabs validate structure when labels exist.
- Using pipelines to keep preprocessing + modeling reproducible.

## Quick Start
```bash
git clone https://github.com/Joe-Naz01/clustering.git
cd clustering
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
