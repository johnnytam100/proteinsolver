# ProteinSolver

[![binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/git/https%3A%2F%2Fmybinder%3AhTGKLsjmxRS8xNyHxRJB%40gitlab.com%2Fostrokach%2Fproteinsolver.git/v0.1.25)
[![docs](https://img.shields.io/badge/docs-v0.1.25-blue.svg)](https://ostrokach.gitlab.io/proteinsolver/v0.1.25/)
[![poster](https://img.shields.io/static/v1?label=poster&message=html&color=orange)](https://ostrokach-posters.gitlab.io/2019-12-13-neurips-poster/7ad67cfdf35a4e3e8346e293dc444074/)
[![conda](https://img.shields.io/conda/dn/ostrokach-forge/proteinsolver.svg)](https://anaconda.org/ostrokach-forge/proteinsolver/)
[![pipeline status](https://gitlab.com/ostrokach/proteinsolver/badges/v0.1.25/pipeline.svg)](https://gitlab.com/ostrokach/proteinsolver/commits/v0.1.25/)
[![coverage report](https://gitlab.com/ostrokach/proteinsolver/badges/master/coverage.svg?job=docs)](https://ostrokach.gitlab.io/proteinsolver/v0.1.25/htmlcov/)

## Description

ProteinSolver is a deep neural network which learns to solve (ill-defined) constraint satisfaction problems (CSPs) from training data. It has shown promising results both on a toy problem of learning how to solve Sudoku puzzles and on a real-world problem of designing protein sequences that fold into a predetermined geometric shape.

## Demo notebooks

The following notebooks can be used to explore the basic functionality of `proteinsolver`.

| Notebook name               | MyBinder                                                                                                                                                                                                                        | Description                                                                                                                                                                                |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `20_sudoku_demo.ipynb`      | [![binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/git/https%3A%2F%2Fmybinder%3AhTGKLsjmxRS8xNyHxRJB%40gitlab.com%2Fostrokach%2Fproteinsolver.git/v0.1.25?filepath=proteinsolver%2Fnotebooks%2F20_sudoku_demo.ipynb)      | Use a pre-trained network to solve a single Sudoku puzzle.                                                                                                                                 |
| `06_sudoku_analysis.ipynb`  | [![binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/git/https%3A%2F%2Fmybinder%3AhTGKLsjmxRS8xNyHxRJB%40gitlab.com%2Fostrokach%2Fproteinsolver.git/v0.1.25?filepath=proteinsolver%2Fnotebooks%2F06_sudoku_analysis.ipynb)  | Evaluate a network trained to solve Sudoku puzzles using the validation<br>and test datasets.<br>_(This notebook is resource-intensive and is best ran on a machine with a GPU)._          |
| `20_protein_demo.ipynb`     | [![binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/git/https%3A%2F%2Fmybinder%3AhTGKLsjmxRS8xNyHxRJB%40gitlab.com%2Fostrokach%2Fproteinsolver.git/v0.1.25?filepath=proteinsolver%2Fnotebooks%2F20_protein_demo.ipynb)     | Use a pre-trained network to design sequences for a single protein geometry.                                                                                                               |
| `06_protein_analysis.ipynb` | [![binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/git/https%3A%2F%2Fmybinder%3AhTGKLsjmxRS8xNyHxRJB%40gitlab.com%2Fostrokach%2Fproteinsolver.git/v0.1.25?filepath=proteinsolver%2Fnotebooks%2F06_protein_analysis.ipynb) | Evaluate a network trained to reconstruct protein sequences using the<br>validation and test datasets.<br>_(This notebook is resource-intensive and is best ran on a machine with a GPU)._ |

Other notebooks in the `notebooks/` directory show how to perform more extensive validations of the networks and how to train new networks.

## Docker images

Docker images with all required dependencies are provided at: <https://gitlab.com/ostrokach/proteinsolver/container_registry>.

To evaluate a proteinsolver network from a Jupyter notebook, we can run the following:

```bash
docker run -it --rm -p 8000:8000 registry.gitlab.com/ostrokach/proteinsolver:v0.1.25 jupyter notebook --ip 0.0.0.0 --port 8000
```

## Installation

We recommend installing `proteinsolver` into a clean conda environment using the following command:

```bash
conda create -n proteinsolver -c pytorch -c conda-forge -c kimlab -c ostrokach-forge proteinsolver
conda activate proteinsolver
```

## Development

First, use `conda` to install `proteinsolver` into a new conda environment. This will also install all dependencies.

```bash
conda create -n proteinsolver -c pytorch -c conda-forge -c kimlab -c ostrokach-forge proteinsolver
conda activate proteinsolver
```

Second, run `pip install --editable .` inside the root directory of this package. This will force Python to use the development version of our code.

```bash
cd path/to/proteinsolver
pip install --editable .
```

## Pre-trained models

Pre-trained models can be downloaded using `wget` by running the following command _in the root folder of the `proteinsolver` repository_:

```bash
wget -r -nH --cut-dirs 1 --reject "index.html*" "http://models.proteinsolver.org/v0.1/"
```

## Training and validation datasets

Data used to train and validate the "proteinsolver" network to solve Sudoku puzzles and reconstruct protein sequences can be downloaded from <http://deep-protein-gen.data.proteinsolver.org/>:

```bash
wget -r -nH --reject "index.html*" "http://deep-protein-gen.data.proteinsolver.org/"
```

## Environment variables

- `DATAPKG_DATA_DIR` - Location of training and validation data.

## Acknowledgements

<div align="center">
<img src="docs/_static/acknowledgements.svg" width="45%" />
</div>

## References

- Alexey Strokach, David Becerra, Carles Corbi-Verge, Albert Perez-Riba, Philip M. Kim. _Fast and flexible design of novel proteins using graph neural networks_. <https://doi.org/10.1101/868935>
