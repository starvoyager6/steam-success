# Steam Success

<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

We're looking at Steam games — prices, tags, reviews, and concurrent players — to see what actually tracks with success.

## Environment

```sh
conda env create -f environment.yml
conda activate steam-success
```

## Data

The raw dump is not committed (`data/` is gitignored). Get a Kaggle API token, then download [130k Steam Games: Prices, Tags, Reviews, CCU](https://www.kaggle.com/datasets/sibamsamanta07/130k-steam-games-prices-tags-reviews-ccu) into `data/raw`.

1. Create a token at [kaggle.com/settings/api](https://www.kaggle.com/settings/api) (Generate New Token) and copy it.

2. Save it locally (replace the placeholder with your token):

```sh
mkdir -p ~/.kaggle && echo 'YOUR_KAGGLE_API_TOKEN' > ~/.kaggle/access_token && chmod 600 ~/.kaggle/access_token
```

3. Activate this project's conda env so the `kaggle` CLI is available, then from the repo root:

```sh
kaggle datasets download sibamsamanta07/130k-steam-games-prices-tags-reviews-ccu \
  -p data/raw --unzip
```

## Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see www.mkdocs.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for 
│                         steam_success and configuration for tools like black
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8
│
└── steam_success   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes steam_success a Python module
    │
    ├── config.py               <- Store useful variables and configuration
    │
    ├── dataset.py              <- Scripts to download or generate data
    │
    ├── features.py             <- Code to create features for modeling
    │
    ├── modeling                
    │   ├── __init__.py 
    │   ├── predict.py          <- Code to run model inference with trained models          
    │   └── train.py            <- Code to train models
    │
    └── plots.py                <- Code to create visualizations
```

--------

