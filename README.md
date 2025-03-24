# KNSI GOLEM Template Repository
<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

Template repository for KNSI GOLEM projects made from cookiecutter data science template.
This repository goal is to provide out of the box boiler plate code with clean project files structure.
Additionally template Github CI is provided with pytest and flake8 checks implemented.

## How to use
Each functionality from making plots to training models are given it's respective file in the `src` folder - full description of files structure is provided in `Procject Organization` paragraph.

Example usage:
```
python3 -m src.dataset
```

## Additional informations
### venv
Users are advised to use venv.
Example usage:

```
python3 -m venv .venv  # create venv
source .venv/bin/activate  # activate venv
pip install -r requirements.txt  # install requirements to venv
```
And install requirements from `requirements.txt`. Base python libs like pytests were already added to requirements.
### dotenv
Another fantastic tool is dotenv that let's configure environment variables in `.env` file.
Lib `python-dotenv` was already included in requirements.

.env file:
```
API_KEY = "KNSI_GOLEM_API_KEY"
```

Python file:
```
from dotenv import load_dotenv
import os

load_dotenv()

api_key = os.getenv("API_KEY")
```

## Project Organization

```
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
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8 and pytest
│
└── src   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes src a Python module
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