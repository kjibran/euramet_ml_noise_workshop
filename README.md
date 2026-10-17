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

## Option 1: Google Colab (recommended)

Nothing to install. You only need a Google account.

1. Click a button below. The notebook opens in Colab.
2. Run the first code cell. It downloads the data and prints `Data folder found: True`.
3. Run the other cells from top to bottom.

Do step 2 again in each notebook, because every Colab notebook runs on its own machine. If the download fails,
the cell asks you to upload `ml_noise_workshop.zip`, which your tutor can give you.

| Notebook | |
|---|---|
| 00 Explore the data | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kjibran/euramet_ml_noise_workshop/blob/main/00_noise_data_exploration.ipynb) |
| 01 Calibrate | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kjibran/euramet_ml_noise_workshop/blob/main/01_noise_calibration.ipynb) |
| 02 Detect drift | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kjibran/euramet_ml_noise_workshop/blob/main/02_noise_drift_detection.ipynb) |

Changes you make in Colab are lost when you close the tab. To keep them, use *File* → *Save a copy in Drive*.

## Option 2: On your own computer

### 1. Get the files

Download the folder in one of two ways:

- From GitHub: click the green **Code** button at the top of this page, then **Download ZIP**.
- Or use `ml_noise_workshop.zip` from your tutor.

Unzip it to a place you can find again, for example your Documents folder. Inside you should see the three
notebooks and a `data` folder.

### 2. Install uv (once)

[uv](https://docs.astral.sh/uv/) installs Python and all the packages for this workshop in one step,
inside the workshop folder only. Open a terminal and run:

**Windows** (PowerShell):

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

**macOS and Linux**:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Close the terminal and open a new one, so that the `uv` command is found.

### 3. Start the notebooks

In the terminal, go to the unzipped folder and start JupyterLab. Replace the path with your own:

```bash
cd path/to/the/unzipped/folder
uv sync
uv run jupyter lab
```

`uv sync` takes a minute the first time. JupyterLab then opens in your browser. Double-click
`00_noise_data_exploration.ipynb` to start. If JupyterLab asks for a kernel, choose **Python 3**.

To stop JupyterLab, press `Ctrl`+`C` in the terminal.

### Already have Python?

If you already use Python 3.10 or newer and do not want uv, install the packages yourself and start JupyterLab
from the unzipped folder:

```bash
pip install polars scikit-learn matplotlib jupyterlab
jupyter lab
```

### Cleaning up afterwards

- Delete the unzipped folder. This also removes the `.venv` folder with everything `uv sync` installed.
- Optional: clear the uv download cache with `uv cache clean`.
- Optional: remove uv itself, following the [uninstall guide](https://docs.astral.sh/uv/getting-started/installation/#uninstallation).
