Predicting Flight Depareture Delays
==============================

Flight delays heavily affect customer experience and satisfaction. This would lead to negative effects on airline companies' revenue, such as customers buying from other air carriers instead. Continuous patterns of delays are detrimental to an airline company’s reputation, leaving them with dissatisfied customers and catastrophic logistics. AAA is tasked with providing insight into airline departure delays. For example, an analysis on which carriers are most and least reliable for on-time departure. This would provide a starting point for understanding the factors impacting delays. 

Further analysis should be conducted to determine an insightful guide for airline strategic leaders. The guide will include features in the data set that are most correlated with departure delays, models that can accurately predict a departure delay, and explanations of the reason for departure delays of flights in the month of December. These insights will provide the business leaders with better understanding on remediation efforts to mitigate delays. Thus, a successful solution will be able to reduce the number of late departures and elevate customer satisfaction.


Collabortors 
- [Jimmy Nguyen](https://github.com/jimmy-nguyen-data-science)
- [Roberto Cancel](https://github.com/rcancel3)
- [Maha]()


To clone this repository onto your device, use the commands below:

	1. git init
	2. git clone git@github.com:jimmy-nguyen-data-science/Predict-Food-Recipe-Ratings.git


Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
