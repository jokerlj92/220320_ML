# CLAUDE.md

This file provides context for AI assistants working in this repository.

## Repository Overview

This is a **course assignment repository** containing two independent ML homework projects:

1. **CS224S HW3 — End-to-End Speech Recognition** (Stanford, Spring 2022)
   - Implemented in `CS224S_HW3_2022_E2E（副本）.ipynb`
   - Covers CTC, multi-task learning, and CTC-Attention architectures

2. **Time Series Forecasting HW1**
   - Documented in `README.md`
   - References a `main.py` CLI script and `dataset/` directory (not checked in)

3. **Algorithms & Algebra Notes**
   - `AA-HW.md` — brief note on Polynomial Identity Testing / Schwartz-Zippel lemma
   - `AA_HW` — plain-text companion file

There is no shared code between the two ML projects. Each is self-contained.

## Repository Structure

```
220320_ML/
├── CS224S_HW3_2022_E2E（副本）.ipynb   # Speech recognition assignment notebook
├── README.md                            # Time series forecasting instructions
├── AA-HW.md                             # Algorithms homework note (Markdown)
├── AA_HW                                # Algorithms homework note (plain text)
└── CLAUDE.md                            # This file
```

No `requirements.txt`, `setup.py`, `pyproject.toml`, `Makefile`, or CI configuration exists. Dependencies are installed inline in the notebook.

## Project 1: CS224S Speech Recognition Notebook

### Environment

- Designed for **Google Colab** with a V100 GPU
- Requires Google Drive mount for data persistence
- Dependencies installed via pip inside the notebook:
  - `pytorch-lightning==1.9.3`
  - `librosa`, `h5py`, `wandb`, `numpy`, `scikit-learn`

### Dataset

Downloaded at runtime from Stanford servers:

```
harper_valley_bank_minified.zip
  ├── data.h5        # Audio waveforms as numpy arrays
  └── labels.npz     # Transcripts and metadata
```

### Notebook Structure (7 Parts)

| Part | Topic |
|------|-------|
| 1 | ML Speech Data Pipeline — `HarperValleyBank` PyTorch Dataset |
| 2 | CTC Neural Network baseline |
| 3 | CER analysis and inference |
| 4 | Auxiliary tasks for multi-task learning (intent classification) |
| 5 | Joint CTC-Attention model |
| 6 | Model comparison and selection |
| 7 | Optional LAS (Listen, Attend and Spell) implementation |

### Key Classes / Concepts

- `HarperValleyBank` — custom `torch.utils.data.Dataset` wrapping HDF5 audio
- CTC loss training via PyTorch Lightning `LightningModule`
- `WandbLogger` for experiment tracking
- `ModelCheckpoint` callback for saving best checkpoints
- Evaluation metric: **CER** (Character Error Rate)

### Running the Notebook

Open in Google Colab; run cells sequentially. The setup cell installs all dependencies. Data download happens automatically in Part 1.

## Project 2: Time Series Forecasting

### Environment

- Python 3.9
- Dependencies: `numpy==1.25.2`, `pandas==2.0.3`, `scikit-learn==1.3.0`, `matplotlib==3.7.2`, `argparse==1.4.0`

### Running

```bash
# Custom dataset
python main.py --data_path ./dataset/Custom/national_illness.csv \
               --dataset Custom --model LinearRegression --transform BoxCox

# ETT dataset
python main.py --data_path ./dataset/ETT-small/ETTh1.csv \
               --dataset ETT --model LinearRegression --transform BoxCox

# M4 dataset
python main.py --data_path ./dataset/m4 \
               --train_data_path /Daily-train.csv \
               --test_data_path /Daily-test.csv \
               --dataset M4 --model LinearRegression --transform BoxCox
```

### Available Options

| Argument | Choices |
|----------|---------|
| `--model` | `ZeroForecast`, `MeanForecast`, `LinearRegression`, `ExponentialSmoothing` |
| `--transform` | `IdentityTransform`, `Normalization`, `Standardization`, `MeanNormalization`, `BoxCox` |
| `--dataset` | `Custom`, `ETT`, `M4` |

### Evaluation Metrics

MSE, MAE, MAPE, SMAPE, MASE

## Development Conventions

### Language & Style

- All code is Python, primarily in Jupyter notebooks
- No linting or formatting tools are configured; follow PEP 8 informally
- Markdown cells document each task (Tasks are numbered, e.g., Task 1.1, 2.1)

### Notebooks

- Do not reorder cells; the notebook is designed to run top-to-bottom
- Keep Google Colab compatibility — avoid local-only filesystem assumptions
- Experiment results should be logged to Weights & Biases (`wandb`)

### No CI/CD

There are no GitHub Actions or test runners. Validation is done manually by running notebook cells or the CLI script.

### Git

- Branch for AI-assisted work: `claude/add-claude-documentation-za4BK`
- Main branch: `main`
- Commit messages have historically been in English or Chinese (mixed)
- No merge-commit discipline enforced

## Key Gotchas for AI Assistants

1. **No installable package** — there is no `setup.py` or `pyproject.toml`. Do not attempt to install the project itself.
2. **Data not in repo** — datasets must be downloaded at runtime; do not assume local paths exist.
3. **Notebook-first** — the primary artifact is the `.ipynb` file, not standalone `.py` scripts.
4. **Chinese filename** — the notebook filename contains Chinese characters and a parenthetical; handle with care in shell commands (quote the path).
5. **Two separate projects** — changes to the speech notebook have no relation to the time series README and vice versa.
6. **No test suite** — there are no automated tests; correctness is verified by expected CER / metric values inline in the notebook.
