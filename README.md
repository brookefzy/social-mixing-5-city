# Social Mixing in Five Cities

This repository supports the paper *Latent patterns of urban mixing in mobility analysis across five global cities* by Fan et al. (2026).

The code in this repo is organized as notebook-based figure reproduction. The required study data are distributed in this repository as `data.zip`.

## Repository layout

- `script/`: Jupyter notebooks used to reproduce the figures currently ported into this repo
- `data.zip`: compressed study data that should be unpacked after cloning
- `requirements.txt`: minimal Python dependencies needed to run the notebooks

## Replication quick start

Clone the repository:

```bash
git clone https://github.com/brookefzy/social-mixing-5-city.git
cd social-mixing-5-city
```

Unzip the study data from the repository root:

```bash
unzip data.zip
```

This creates a local `data/` directory with the parquet and CSV files used by the notebooks. On macOS, `unzip` may also create an extra `__MACOSX/` folder. It is not needed and can be removed:

```bash
rm -rf __MACOSX
```

After unzipping, your top-level folder should include:

```text
data/
  c_individual_all.parquet
  c_individual_all_osm_home_15_place_15.parquet
  poi_exposure_osm_all_fpTrue_wm=osm_15min.csv
  poi_exposure_osm_all_fpTrue_wm=osm_15minw.csv
  poi_exposure_osm_all_fpTrue_wm=osm_1260m.csv
  poi_exposure_osm_all_fpTrue_wm=osm_1260mw.csv
script/
requirements.txt
README.md
```

## Python environment

Create and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install the required packages:

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

If you prefer Conda, the equivalent flow is:

```bash
conda create -n social-mixing python=3.12 -y
conda activate social-mixing
pip install -r requirements.txt
```

## Running the notebooks

Start Jupyter from the repository root:

```bash
jupyter notebook
```

Then open the notebooks in `script/`.

Run the cells in order. The notebooks are written to read data from the repo-local `data/` directory, so launching Jupyter from the repository root is the safest default.

## Available local inputs

The current notebooks use these local files:

- `script/fig1.ipynb`: `data/c_individual_all_osm_home_15_place_15.parquet`
- `script/fig2.ipynb`: `data/c_individual_all.parquet`
- `script/fig3.ipynb`: `data/c_individual_all_osm_home_15_place_15.parquet`
- `script/fig5.ipynb`: uses files under `data/` as configured inside the notebook

## Notes on fonts and rendering

The notebooks keep the original paper styling where possible, including `Times New Roman`. If that font is not installed on your machine, Matplotlib will fall back to a local serif font such as `DejaVu Serif`. The figures will still run, but text rendering may differ slightly from the paper figures.

## Troubleshooting

If `unzip data.zip` does not create the `data/` directory, make sure you are running the command from the repository root.

If a notebook raises a file-not-found error, verify that the expected files are present under `data/` and that you launched Jupyter from the repository root rather than from inside `script/`.

If Jupyter is not installed yet, install it into the same environment:

```bash
pip install notebook ipykernel
```

## Citation

If you use this repository, please cite the associated paper by Fan et al. (2026).
