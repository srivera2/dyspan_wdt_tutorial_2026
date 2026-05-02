---
layout: page
title: Local Setup
---

Our instructions assume that you are comfortable with creating and modifying conda environments:

[miniconda](https://docs.conda.io/projects/conda/en/stable/user-guide/install/index.html)

## Create the Conda Environment
```bash
conda create --yes --name g2sm --channel conda-forge pdal python=3.12
conda activate g2sm
```

## Clone and Install geo2sigmap:
```bash
git clone https://github.com/functions-lab/geo2sigmap
cd geo2sigmap/package
pip install .
cd ..
```

## Install Required Packages:
```bash
git checkout /dyspan2026
pip install -r requirements.txt
```

## Launch Jupyter
```bash
jupyter notebook
```

Open the URL printed in your terminal (usually `http://localhost:8888`) and navigate to the `/research/examples` folder to begin.

The tutorial notebooks are located in ```\research\examples```. 

## Starting a notebook

1. On the left-plane, left-click a notebook filename to open it.
2. From the menu bar, select **Kernel → Restart & Run All** to execute all cells, or step through them one at a time with **Shift + Enter**.
3. There are several opportunities to customize the design of notebook cells. We encourage modifying scene parameters to become familiar with the capabilities offered in ```sionna-rt```.

## Troubleshooting

1. If you have any conflicting package versions, make sure you haven't attempted to use an existing conda environment. It's best practice to start from scratch.
2. Before walking through the tutorial, make sure you have enough space to generate/store each ray tracing scene. There is decent memory overhead required for creating LiDAR terrain ```.ply``` files. If at any point your notebook fails, we will provide you access to a container on our JupyterHub server.