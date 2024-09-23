# Learning ML

## Installation

### Using a package manager with and an environment YAML file (Recommended)

Ensure you haven't already installed this environment:
```
$ conda remove --name learning-ml --all -y
```

The steps are:
* Create a new environment with the OS specific YAML file,
* Install any extra software directly from source (see "Installing Dependencies from Source").

OSX ARM64 (M series CPUs):
```
$ conda env create --name gfiglearning-ml --file=environment-macos-arm.yml -y
```

OSX x86 (Intel CPUs):
```
$ conda env create --name learning-ml --file=environment-macos-x86.yml -y
```
[environment-macos-x86.yml](environment-macos-x86.yml)
Windows:
```
$ conda env create --name learning-ml --file=environment-windows.yml -y
```

### Steps to reproduce YAML file

You shouldn't need to do this - but if the conda create fails above this gives you the steps to reproduce the
environment.

#### For MacOS ARM
```
$ conda create --name binf-7000-2024-spatial python=3.12 -y
$ conda activate binf-7000-2024-spatial
$ conda install -c conda-forge scanpy scipy joblib scikit-learn pytorch torchvision jupyterlab iprogress ipywidgets python-igraph gprofiler-official leidenalg -y
```

#### For MacOS x86
```
$ conda create --name binf-7000-2024-spatial python=3.12 -y
$ conda activate binf-7000-2024-spatial
$ conda install -c conda-forge scanpy scipy joblib scikit-learn pytorch torchvision jupyterlab iprogress ipywidgets python-igraph gprofiler-official leidenalg -y
```

#### For Windows

```
$ conda create --name binf-7000-2024-spatial python=3.12 -y
$ conda activate binf-7000-2024-spatial
$ conda install -c conda-forge scanpy scipy joblib scikit-learn pytorch torchvision jupyterlab iprogress ipywidgets python-igraph leidenalg -y
$ conda install -c bioconda gprofiler-official -y
```

#### For All

```
$ python -m pip install --use-pep517 -r requirements.txt
```

#### Generate Yaml

```
$ conda env export > environment-[linux|windows|macos-arm|macos-x86].yml
```

## Known Bugs and Issues

* When using Leiden clustering you get the following error on Windows https://github.com/scverse/scanpy/issues/2969
* Louvain clustering is deprecated/no longer supported https://github.com/scverse/scanpy/issues/1283, https://scanpy.readthedocs.io/en/stable/generated/scanpy.tl.louvain.html
