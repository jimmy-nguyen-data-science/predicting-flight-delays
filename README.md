Predicting Flight Departure Delays
==============================

Flight delays heavily affect customer experience and satisfaction. This would lead to negative effects on airline companies' revenue, such as customers buying from other air carriers instead. Continuous patterns of delays are detrimental to an airline company’s reputation, leaving them with dissatisfied customers and catastrophic logistics. We are tasked with providing insight into airline departure delays. For example, an analysis on which carriers are most and least reliable for on-time departure. This would provide a starting point for understanding the factors impacting delays. 

Further analysis should be conducted to determine an insightful guide for airline strategic leaders. The guide will include features in the data set that are most correlated with departure delays, models that can accurately predict a departure delay, and explanations of the reason for departure delays of flights in the month of December. These insights will provide the business leaders with better understanding on remediation efforts to mitigate delays. Thus, a successful solution will be able to reduce the number of late departures and elevate customer satisfaction.


# Collaborators  
- [Jimmy Nguyen](https://github.com/jimmy-nguyen-data-science)
- [Roberto Cancel](https://github.com/rcancel3)
- [Maha Jayapal](https://github.com/MahaJayapal)


To clone this repository onto your device, use the commands below:

	1. git init
	2. git clone git@github.com:jimmy-nguyen-data-science/predicting-flight-delays.git


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

# How to download data and upload data into S3 Buckets

- Files can be found in the \src\raw_data\ folder
- Alternatively, files can be downloaded here from the original source: 

	https://www.kaggle.com/datasets/threnjen/2019-airline-delays-and-cancellations


**For creating and uploading S3 public bucket (Manually)**
-----	

	1. Git clone this repository following the instructions above 
	2. Create AWS account to use services such as S3 Buckets and SageMaker
	3. Go to the S3 page
	4. Click create bucket, make a new folder called raw_data and upload the following files manually:
		- B43_AIRCRAFT_INVENTORY.csv
		- ONTIME_REPORTING_12.csv
		- P10_EMPLOYEES.csv
		- airports_list.csv
		- CARRIER_DECODE.csv
		- airport_weather_dec_2019.csv
	4. Make this s3 bucket public for collaboration among teammates
	5. Create a new, separate private bucket to upload cleaned and transformed data for future sagemaker notebooks


-----

**For creating S3 public bucket on AWS CL**

- Specify the file path for where you downloaded the data sets
-----
	aws s3 mb s3://ads-508-airline
	aws s3 cp file_path s3://ads-508-airline
	aws s3api put-bucket-acl --bucket ads-508-airline --acl public-read
	 
-----



**For creating S3 private bucket with Sagemaker notebooks** 
- Use the following code and commands in a Sagemaker notebook with the following code:

-----
		
		# Set-up

		sess = sagemaker.Session()
		bucket = sess.default_bucket()
		role = sagemaker.get_execution_role()
		region = boto3.Session().region_name
		
		# Private S3 Bucket
		s3_private_path_csv = "s3://{}/ads508/data".format(bucket)
		
		# Upload downloaded data files into private s3 bucket 
		
		!aws s3 mb $s3_private_path_csv
		!aws s3 cp $file_path $s3_private_path_csv/ 

-----


<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
