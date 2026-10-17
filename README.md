# Machine Learning Workshop, Noise Track: Start Here

Goal: calibrate low-cost noise sensors with machine learning and detect when they drift.

```text
 00 explore          ──>   01 calibrate               ──>   02 detect drift
 how good is the data?     features, model, split           which node, when, how big?
```

## The Notebooks

| Notebook | Goal | Time | Participant output |
|---|---|---|---|
| [`00_noise_data_exploration.ipynb`](00_noise_data_exploration.ipynb) | Explore data quality, find and fix a clock error | 35 min | Slide 1 of the template |
| [`01_noise_calibration.ipynb`](01_noise_calibration.ipynb) | Calibrate step by step: features, model, random or time split | 50 min | Slide 2 |
| [`02_noise_drift_detection.ipynb`](02_noise_drift_detection.ipynb) | Find drifting nodes with four methods, decide what to do | 60 min | Slides 3 to 5 |

Fill in `Group_results_template_noise.pptx` as you go.

## The Data

Three low-cost MEMS noise nodes next to a Class 1 monitoring terminal, 1 September to 28 December 2025,
`LAeq,10min` in dB, plus wind speed and rain from a weather station. All files are in `data/`.

**The data are synthetic.** They were generated to behave like real co-location data, with typical faults hidden in them.
Because the truth is known, every method can be checked against it at the end.

## Running the Notebooks

**Google Colab** (recommended): open a notebook in Colab and run the first code cell. It downloads the data from
GitHub. If that fails, it asks you to upload `ml_noise_workshop.zip`, which your tutor gives you. Run this cell again in
each notebook, because every Colab notebook runs on its own machine. Polars, scikit-learn and matplotlib are already
installed on Colab.

Open directly in Colab:
[00](https://colab.research.google.com/github/kjibran/euramet_ml_noise_workshop/blob/main/00_noise_data_exploration.ipynb) ·
[01](https://colab.research.google.com/github/kjibran/euramet_ml_noise_workshop/blob/main/01_noise_calibration.ipynb) ·
[02](https://colab.research.google.com/github/kjibran/euramet_ml_noise_workshop/blob/main/02_noise_drift_detection.ipynb)

**On your own computer**: you need Python 3.10 or newer and [uv](https://docs.astral.sh/uv/). In this folder:

```bash
uv sync           # installs polars, scikit-learn, matplotlib and JupyterLab
uv run jupyter lab
```

Afterwards you can delete the `.venv` folder to remove everything that was installed.
