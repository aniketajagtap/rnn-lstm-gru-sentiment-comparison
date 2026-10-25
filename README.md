# RNN vs LSTM vs GRU: Sentiment Analysis Comparison

# RNN vs LSTM vs GRU: Sentiment Analysis Comparison

This project compares three recurrent neural-network architectures—Simple RNN, LSTM, and GRU—on movie-review sentiment classification using PyTorch.

## Project overview

The notebook loads the IMDB sentiment dataset, preprocesses review text, creates a vocabulary, encodes and pads reviews, trains a model for each recurrent cell type, and compares predictive accuracy and training time.

### Workflow

1. Load the IMDB review CSV.
2. Clean review text and build a vocabulary capped at 10,000 tokens.
3. Convert reviews into token sequences with a maximum length of 200.
4. Split the dataset into training and test sets (80/20).
5. Train the same model framework using Simple RNN, LSTM, and GRU cells.
6. Compare final test accuracy, loss curves, and total training time.

## Recorded results

The notebook's saved execution output reports the following values:

| Model | Test accuracy | Training time |
|---|---:|---:|
| Simple RNN | 85.24% | 535.23 s |
| LSTM | 85.22% | 494.15 s |
| GRU | 86.77% | 1109.33 s |

These are values from the saved notebook output, not guaranteed results on another machine or run. **Before publishing, reconcile the separate comparative-analysis markdown cell in the notebook**, because its approximate accuracy values do not match the saved execution output above.

## Tech stack

- Python
- PyTorch
- pandas
- scikit-learn
- Matplotlib
- Jupyter Notebook

## Dataset setup

The IMDB CSV is **not included** in this repository. Obtain the dataset from a source whose terms permit your use, and place the CSV here:

```text
data/
└── IMDB Dataset.csv
```

The CSV is expected to contain at least these columns:

- `review` — review text
- `sentiment` — sentiment label, expected to be `positive` or `negative`

The notebook uses the relative path `data/IMDB Dataset.csv`; launch Jupyter from the repository root.

## Installation

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

macOS/Linux:

```bash
source .venv/bin/activate
python -m pip install -r requirements.txt
```

## Run the notebook

```bash
jupyter notebook RNN_vs_LSTM_vs_GRU.ipynb
```

Run the cells from top to bottom after placing the dataset in `data/`. Training all three models may take several minutes or longer depending on hardware.

## Repository structure

```text
rnn-lstm-gru-sentiment-comparison/
├── RNN_vs_LSTM_vs_GRU.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── data/                  # Local dataset; not committed
```

## Limitations and interpretation

- The dataset is not bundled with the repository.
- Training time varies significantly by CPU/GPU, software versions, and hardware acceleration.
- The notebook uses a simple vocabulary and fixed-length padding/truncation.
- The saved notebook's narrative summary and captured execution output disagree on some reported accuracy values; rerun the notebook and update the summary before relying on the figures.
- The current experiment is a useful comparison exercise, but robust conclusions require repeated runs, controlled seeds, and more detailed metrics such as precision, recall, F1-score, and confusion matrices.

## License

No license has been specified. Add a `LICENSE` file if you want to define reuse and distribution terms.
