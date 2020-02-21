# MARC: a robust method for multiple-aspect trajectory classification via space, time, and semantic embeddings

Source code of the paper **MARC: a robust method for multiple-aspect trajectory classification via space, time, and semantic embeddings**, accepted for publication in International Journal of Geographical Information Science (IJGIS).

[ [publication](https://www.tandfonline.com/doi/abs/10.1080/13658816.2019.1707835?journalCode=tgis20) ] [ [preprint](./preprint.pdf) ] [ [bibtex](./citation.bib) ]

### Setup

1. In order to run the code you first need to install all the Python dependencies listed in `requirements.txt`. You can do that with pip (works only with Python 3, tested with Python 3.6.7):
    ```
    pip install -r requirements.txt
    ```

2. Or if you use the [Miniconda](https://docs.conda.io/en/latest/miniconda.html) environment manager you can just run the following to create an environment with Python 3.6.7 and all required dependencies (replace `ENV_NAME` with whatever name you'd like):
    ```
    conda env create -f environment.yml --name ENV_NAME
    ```
    And then activate it with:
    ```
    conda activate ENV_NAME
    ```

### Usage

1. You can run the classifier with the following command:
    ```
    python multi_feature_classifier.py TRAIN_FILE TEST_FILE RESULTS_FILE DATASET_NAME EMBEDDING_SIZE MERGE_TYPE RNN_CELL
    ```
    Where:
    - `TRAIN_FILE`: The input CSV training file.
    - `TEST_FILE`: The input CSV test file.
    - `RESULTS_FILE`: The destination CSV results file.
    - `DATASET_NAME`: Label with the dataset name. This will be written in the results file as the dataset name.
    - `EMBEDDING_SIZE`: The embedding size of the attributes.
    - `MERGE_TYPE`: How attributes should be aggregated. It can be one of {add, average, concatenate}.
    - `RNN_CELL`: The recurrent cell used in the network. It can be one of {gru, lstm}.
2. For instance:
    ```
    python multi_feature_classifier.py data/foursquare_nyc/train.csv data/foursquare_nyc/test.csv results.csv FoursquareNYC 100 concatenate lstm
    ```
