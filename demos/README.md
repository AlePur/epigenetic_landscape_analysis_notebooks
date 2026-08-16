# SparSCit demos (tutorial)

Short notebooks for the core methods — not a full paper reanalysis.

## Setup

```bash
cd path/to/scit-package
# nix-shell
# venv is activated by shell.nix
pip install -e .
pip install -r requirements.txt
pip install jupyter ipykernel nbconvert
```

Pins that matter for this stack (in package `requirements.txt`):

- `pandas>=2.2,<3` — anndata h5ad write
- `matplotlib>=3.7,<3.9` — `matplotlib.cm.get_cmap` used by SparSCit
- `ipywidgets` — `tqdm.notebook` progress bars in landscape
- `ipython>=8.12,<8.24` — works with matplotlib 3.8 + Jupyter

Data: `demos/data/demo.h5ad`

```text
demo.h5ad  — 5000 cells × ~27k bins, layers acet / meth
```

## Run order

| Notebook | Topic |
|----------|--------|
| `notebooks/01_load_and_embed.ipynb` | Load, filter, multiview spectral, knn, leiden, UMAP |
| `notebooks/02_landscape.ipynb` | Scaffold + landscape embedding |
| `notebooks/03_mark_activity.ipynb` | Random neighborhoods → activity → binary marks |
| `notebooks/04_grid_and_correlation.ipynb` | Griddata + weighted acet–meth correlation |

```bash
cd demos/notebooks
jupyter notebook   # or jupyter lab
```