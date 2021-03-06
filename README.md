Cryptocurrency Recommendation System
==============================

Authors:
Raj Sandhu
Akaash Kapoor
Ali Alvi
Hassan Jallad
Areeb Ul Haq
Ahmad Abuoudeh

This project aims to develop cryptocurrency recommendation systems through analyzing the historical market volatility and descriptiptions of coins through the Word Mover's Distance and Euclidean distance metrics to measure similarity, as well as applying a weighted average of both the Word Mover's Distance and Euclidean Distance for an additional similarity metric.

To run the project successfully, please ensure the Anaconda distrubution of python has been installed (version 3.x should suffice). From here, clone this repo into your working directory. If you wish to perform a clean run, delete all of the data within the raw, interim, processed, bin, and logs folders (data/raw, data/interim, data/processed, data/bin, references/logs). Aditionally delete the data with the models folder, and the figures folder (reports/figures). Next, load this project into JupyterLab. Then run the cryptocurrency_data_ingestion.ipynb notebook. Then run the cryptocurrency_data_transformation.ipynb notebook. Then, the next notebook to be run (cryptocurrency_wmd_similarity_matrix.ipynb) must be opened in google colab. This is to accomodate the memory requirements of the pretrained word embedding model. From here, load in the processed coin dataset into the current runtime in google colab and then run all the cells. Once complete, the Word Mover's Distance similarity matrix will appear in the left hand tab. Download this file and save it in the parent models folder. After this, navigate back to Jupyterlab and run the cryptocurrency_euclidean_distance_similarity.ipynb notebook, then run the cryptocurrency_weighted_average_similarity_matrix.ipynb file. After this, open the coin_data.json file and input the name of your target coin from the ones that are available in the processed coin dataset. Next, run the cryptocurrency_data_analysis.ipynb notebook.

This code has been written to be platform independent, using python libraries to dynamically generate paths.

Required libraries are installed at the notbook level through the pip command.

Raw and cleaned datasets link: https://drive.google.com/drive/folders/1SLigt-jZo5h5-pRbJFqRqJo3vxzbNFLF?usp=sharing
Note: preferred to view data directly in this GitHub repo

Project Organization
------------

    ????????? LICENSE
    ????????? README.md          <- The top-level README for developers using this project.
    ????????? data
    ??????? ????????? external       <- Data from third party sources.
    ??????? ????????? interim        <- Intermediate data that has been transformed.
    ??????? ????????? processed      <- The final, canonical data sets for modeling.
    ??????? ????????? raw            <- The original, immutable data dump.
    ???
    ???
    ????????? models             <- Trained and serialized models, model predictions, or model summaries
    ???   ????????? coin-similarity-matrix-description.csv         <- Word Mover's Distance similarity matrix.
    |   ????????? coin-similarity-matrix-euclidean-distance.csv  <- Euclidean Distance similarity matrix.
    |   ????????? coin-similarity-matrix-weighted-average.csv    <- Weighted Average Distance similarity matrix.
    ???
    ????????? references         <- Data dictionaries, manuals, and all other explanatory materials.
    ???   ????????? logs
    |       ????????? data-ingestion-log.log <- Log file generated by data ingestion notebook that shows the data downloaded, and time of ingestion.
    ????????? reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    ??????? ????????? figures        <- Generated graphics and figures to be used in reporting
    |        ????????? ed-knee-point-plot-usd-coin.jpg               <- Knee plot for Euclidean Distance.
    |        ????????? wmd-knee-point-plot-usd-coin.jpg              <- Knee plot for Word Mover's Distance.
    |        ????????? weighted-average-knee-point-plot-usd-coin.jpg <- Knee plot for Weighted Average.
    |        ????????? histogram-description-plot-usd-coin.jpg       <- histogram for Word Mover's Distance.
    |        ????????? kde-volatility-plot-usd-coin.jpg              <- Kernel Density Estimation plot for Euclidean Distance.
    |        ????????? kde-weighted-metric-average-plot-usd-coin.jpg <- Kernel Density Estimation plot for Weighted Average.
    ???
    ????????? requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    ???                         generated with `pip freeze > requirements.txt`
    ???
    ????????? src                <- Source code for use in this project.
    ???   ???
    ??????? ????????? data           <- Scripts to download or generate data
    ??????? ??????? ????????? cryptocurrency_data_ingestion.ipynb  <- Script that ingests raw data from from CoinCodex.
    ???   ???
    ??????? ????????? features       <- Scripts to turn raw data into features for modeling
    ??????? ??????? ????????? cryptocurrency_data_transformation.ipynb <- Script two transform raw data to a processed dataset for modelling.
    ???   ???
    ??????? ????????? models         <- Scripts to train models and then use trained models to make
    ???   ???   ???                 predictions
    |   |   ????????? coin_data.json                     <- Stores name of target coin.
    |   |   ????????? cryptocurrency_euclidean_distance_similarity_matrix.ipynb <- Computes Euclidean Distance similarity matrix.
    |   |   ????????? cryptocurrency_wmd_similarity_matrix.ipynb                <- Computes Word Mover's Distance similarity matrix.
    |   |   ????????? cryptocurrency_weighted_average_similarity_matrix.ipynb   <- Computes Weighted Average Similarity Matrix.
    ??????? ??????? ????????? cryptocurrency_data_analysis.ipynb                        <- Performs analysis, uses knee method and computes most similar coins to target coin.
    ??????? ??????? 
    ???   ???
    ??????? ????????? visualization  <- Scripts to create exploratory and results oriented visualizations
    ???????     ????????? cryptocurrency_data_visualizations.ipynb <- Creates visualizations and plots to be used in final report.
    ???


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
