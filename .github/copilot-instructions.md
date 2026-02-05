# Copilot Instructions for codespaces-jupyter

## Project Overview
This is a Jupyter-based Python learning and exploration environment hosted in GitHub Codespaces. It contains:
- **Notebooks** (`notebooks/`): Educational Python tutorials and data analysis demonstrations
- **Data** (`data/`): CSV datasets (e.g., `atlantis.csv`) for analysis
- **Scripts** (`first.py`): Standalone Python scripts
- **Environment**: Docker-based dev container with Python 3, Jupyter, and data science libraries

## Development Environment

### Setup & Dependencies
- **Environment Setup**: Automatically configured by `.devcontainer/devcontainer.json`
- **Dependency Management**: `requirements.txt` contains all packages; install via:
  ```bash
  python3 -m pip install -r requirements.txt
  ```
- **Key Libraries**: pandas, matplotlib, torch/torchvision (for image classification), ipywidgets
- **Container**: Ubuntu 20.04.6 LTS with Python 3 pre-installed

### Running Code
- **Notebooks**: Use VS Code's Jupyter extension (pre-configured). Execute cells with Shift+Enter
- **Scripts**: `python3 first.py` or `python first.py`
- **Extensions Installed**: `ms-toolsai.jupyter`, `ms-python.python`

## Project Patterns & Conventions

### Notebook Structure
Notebooks follow a tutorial/exploration pattern:
1. **Educational notebooks** (`1. Introduction to Python 3.ipynb`): Sequential cells demonstrating concepts
2. **Analysis notebooks** (`population.ipynb`, `image-classifier.ipynb`): Load data from `data/`, analyze with pandas/matplotlib
3. **Visualization notebooks** (`matplotlib.ipynb`): Demonstrate plotting techniques

**Pattern**: Each notebook is self-contained; avoid cross-notebook dependencies

### Data Handling
- **Location**: CSV files stored in `data/` directory (e.g., `atlantis.csv`)
- **Access Pattern**: Use pandas to load: `pd.read_csv('data/atlantis.csv')`
- **Scope**: Small datasets suitable for learning; not a production data pipeline

### Code Organization
- **Scripts** (`first.py`): Standalone execution, minimal imports
- **Notebooks**: Interactive exploration with print statements for output
- **Imports**: Standard library + requirements.txt packages only

## AI Agent Guidance

### When Working on Notebooks
1. **Cell-by-cell approach**: Modify individual cells rather than creating new notebooks
2. **Output handling**: Notebook cells produce stdout/stderr—check execution state before suggesting changes
3. **State management**: Variables persist across cells; consider execution order when modifying code

### When Adding Features
1. **Data files**: Place in `data/` if adding datasets
2. **New notebooks**: Name descriptively (e.g., `linear-regression.ipynb`), follow existing tutorial/analysis pattern
3. **Dependencies**: Update `requirements.txt` if adding packages; test with `python3 -m pip install -r requirements.txt`

### Common Tasks
- **Fixing notebook errors**: Check cell execution order and variable definitions in previous cells
- **Adding data analysis**: Use pandas for loading CSV; matplotlib for visualization
- **Handling UI elements**: Use ipywidgets for interactive notebook controls

## Repository Structure Reference
```
.devcontainer/        # Container configuration (do not modify unless changing environment)
notebooks/            # Jupyter notebooks for learning and exploration
data/                 # CSV datasets
first.py              # Example standalone Python script
requirements.txt      # Python dependencies
```

## Notes for AI Agents
- This is a **learning environment**, not production code—focus on clarity and educational value
- **No build/test pipeline**: Notebooks are tested via manual execution
- **No CI/CD**: Changes are local until user publishes to GitHub
- **Codespaces-first**: Assume all work happens in this dev container environment
