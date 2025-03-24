# KNSI GOLEM Template Repository
[![Flake8 Linting](https://github.com/Dnafivuq/golem_template/actions/workflows/lint.yml/badge.svg)](https://github.com/Dnafivuq/golem_template/actions/workflows/lint.yml)
[![Pytest](https://github.com/Dnafivuq/golem_template/actions/workflows/test.yml/badge.svg)](https://github.com/Dnafivuq/golem_template/actions/workflows/test.yml)
<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>


Template repository for KNSI GOLEM projects made from the cookiecutter data science template.
This repository's goal is to provide out-of-the-box boilerplate code with a clean project file structure.
Additionally, the template includes a GitHub CI pipeline with pytest and flake8 checks implemented.


You are free to delete any unnecessary folders and files. However, it is recommended to maintain the overall file structure to ensure clean code and compatibility with other KNSI GOLEM repositories.
## How to use
Each functionality, from making plots to training models, is given its respective file in the `src` folder - a full description of the file structure is provided in the [Project Organization](#project-organization) section.


Example usage:

```bash
python3 -m src.dataset
```

## Additional tips and info
### venv
Users are advised to use a virtual environment (`venv`).


Example usage:
```bash
python3 -m venv .venv  # Create venv  
source .venv/bin/activate  # Activate venv  
pip install -r requirements.txt  # Install requirements to venv  
```
Basic Python libraries like pytest are already included in the requirements.

--------

### dotenv  
Another useful tool is dotenv, which lets you configure environment variables in the `.env` file.  
The `python-dotenv` library has already been added to the requirements.

**.env file example:**
```bash
API_KEY = "KNSI_GOLEM_API_KEY"
```

**Python code example:**
```python
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