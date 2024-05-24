# DTC Project of the week

> [!NOTE]
>
> **What is DVC?** Data Version Control is a free, open-source tool for data management, ML pipeline automation, and experiment management. This helps data science and machine learning teams manage large datasets, make projects reproducible, and collaborate better.

> [!NOTE]
>
> DVC is a tool for data science that takes advantage of existing software engineering toolset. It helps machine learning teams manage large datasets, make projects reproducible, and collaborate better.
>
> [Docs](https://dvc.org/doc) by dvc.ai/iterative.ai

In summary, DVC allows us 
- to track our dataset versions alongside our code. It is another layer on top of git. The data can be stored locally for a solo developer, or remotely (shared network drive, G-Drive, GCP/AWS Buckets) for teams;

- the dataset version is attached to the ML model, so experiments can be reproduced easily;

- compare model's metrics and parameters in logged experiments and the corresponding dataset version that produces that metrics, so there's a lineage traceability;

- DVC+CML (Continuous Machine Learning) facilitates CI/CD for Machine Learning projects
  - **dvc**: data & model versioning, reproducible pipelines
  - **cml**: orchestration, testing and monitoring


## Objective

- Use DVC to track experiments and automate ML Pipelines to process, train and evaluate an ML model. 

## Tech stack

- list libraries and their versions, or point to [environment.yml](environment.yml)


## Dataset

- Download manually via a browser from [source](https://www.kaggle.com/datasets/aslanahmedov/walmart-sales-forecast).

- TODO Download via Kaggle API

```bash
kaggle command
```

## Project Structure

`tree` with below explanations

dvc.yaml files define stages, parameters, metrics, and plots. Stages form the pipeline(s) of a project. Parameters, metrics, and plots are used to evaluate and compare project versions and may be defined within stages or independently.

.dvc files ("dot DVC files") are placeholders to track data files and directories.

.dvcignore files (optional) contain a list of paths for DVC to ignore, which can dramatically increase its operational performance.

Internal files and directories in .dvc/ contain the local configuration file(s), default local cache location, and other utilities that DVC needs to operate.

## TODO Installation

- setup environment
- clone repo 
  - init fresh
    - get dataset
  - get finalized

## Track data

```bash
 dvc add data/features.csv data/stores.csv data/test.csv data/train.csv

100% Adding...|████████████████████████████████████████████████████████████████████████|4/4 [00:00, 43.73file/s]
 
To track the changes with git, run:

    git add data/stores.csv.dvc data/features.csv.dvc data/.gitignore data/test.csv.dvc data/train.csv.dvc

To enable auto staging, run:

    dvc config core.autostage true
```

