This will outline how to retrieve your code, how to retrieve your data, how to retrieve the dependencies (libraries) for running your code, and how to run your code.

# Assignment Details
- @uthor: Ashish Panchal
- GTuser : apanchal33
- Designation: Student- OMSCS Georgia tech
- email : apanchal33@gatech.edu
- Subject : CS7641- Machine learning


# Title : Instructions for implementing Code for Assignment 3 – Unsupervised learning and Dimensionality Reduction
This document details the steps for retrieval of code, data and dependencies, followed by steps for execution of the code.

# The code has directory structure, as follows:


- Assignment 3_main: this is the main folder of the project, containing the following:

    1. File: Code_v1.ipynb: this is the main ipython notebook, which imports data, dependencies, dataset class, loss curve function , learning curve function, learning curve function for neural network, best model identification function, and code for training and testing different algorithms.
    2. Folder: Figure: this folder the base location for saving plots
    3. Folder: Dataset : this folder used to save ADA object of class dataset defined in Code_v1. Each object per dataset contains all the relevant information generated for all algorithms for specific dataset, including loss and learning curves, best found estimators along with scored  for different parameters.
    4. Folder: Raw_data: this folder contains raw csv data downloaded form Kaggle
        - WineQT_2.csv : dataset 1
        - Genderclass.csv : dataset 2 
    5. File: apanchal33-analysis.pdf : Assignment 1 report
    7. File: requirements.txt : lists requirements for the code
    8. ADA: this folder contains intermediate analytical dataset for each analysis.

## 1. Retrieval of the Code:
The code is saved at Sharable Box location : https://gatech.box.com/s/lbcloaskg8zk69tzi8ckxxwykhgu2pl8 

## 2. Retrieval of the data:
There are two datasets used in this code. A copy of these dataset are provided in the code folder, however can be downloaded and added separately. Follow the instructions below.

- Step1 . Create a folder Raw_data if not present inside folder Assignment_1_main:

- Step2. Download the following csv data files and ensure the rename the same as defined in the directory description:
    For both the files navigate to the Kaggle url and click on download button in the data section, please note this may require you to login through your Kaggle profile, if not present, you may create the same using your email id.
    -	Dataset 1:
        - Name: Wine quality dataset:
        - File name :  WineQT_2.csv
        - url : www.kaggle.com/datasets/rajyellow46/wine-quality
    -	Dataset 2:
        - Name: Gender Classification dataset:
        - File name :  Genderclass.csv
        - url : www.kaggle.com/datasets/elakiricoder/gender-classification-dataset




## 3. Retrieval of the Dependencies:
The code uses particular version of different python packages,
These packages with their versions are listed in the requirements.txt file.
Please execute the installation using : ‘pip install -r requirments.txt’ using preferred command line tool or environment from “Assignment_1_main” location.  

## 4. Execution of code:
The code notebook is created in a monolithic fashion. It contains all the required class and function definitions used in the code. And can be executed in a serialized way from first cell to the last.









The code is divided in to 4 parts

1.	Importing of libraries
2.	Handling data:
    - Definition of data_set_module class : an Analytical object for storing analysis objects for specified data. For further details please refer code
    - Importing data, processing data and short EDA.
    - Splitting of training and test data.
    - Creation and saving of dataset object.



3.	Definition of utility functions. There are 2 clustering, 4 dim red. functions, 5 NN helper and 2 visualisation helper  created and used. Please refer the code for more details
    
Clustering
    - run_Kmeans
    - run_EM

Dim. Red.

    - run_PCA
    - run_ICA
    - run_RPA
    - run_IsoMap

NN helper
    - Loss_curve
    - plot_learning_curve
    - GS_get_best_estimator
    - handle_nn
    - epoch_learning_curve

Visual helper
    - create_corr_graphs
    - save_loss_curve




4.	Implementation and Analysis of Algorithms : there are 5 subparts to this section, corresponding	to requirements of the assignment.

4.1 Clustering without DR : for dataset 1 & 2
	- kmeans
	- EM
4.2 Dimensionality Reduction : for dataset 1 & 2
	- PCA
	- ICA
	- RPA
	-IsoMap
4.3 Clustering with DR - dataset 1 & 2
	- Kmeans
		- PCA
		- ICA
		- RPA
		-IsoMap
	- EM
		- PCA
		- ICA
		- RPA
		-IsoMap

4.4 NN with DR: dataset 2
	- PCA
	- ICA
	- RPA
	-IsoMap

4.5 NN with Clustering: dataset 2
	- Kmeans
		- Dataprep
 		- Find best
		- Learning curve
		- Learning curve epoch



Each part create creates objects for analysis and added to respective dataset object. At the same time these also generate  ADA csv files and graphs saved In the ADA and figure folder respectively.


 Kindly node, the code is provided with markdown headings and sections, to make best use of the configuration, please use and IDE which creates a table of content based on the same. (jupyterlab, jupyterbook with TOC ext.)


5. Ways for execution:
    - There are two ways of execution of the code.
    1. Use prebuilt data_set_module objects, which were created while experimentation
        - For this, raise the data_set_module_flag to "True" in the 2nd cell in the load dataset section
        - These object can be directly used for different algorithmic analysis and can be used at any part of code
    2. Create new datasets:
        - Keep the data_set_module_flag to "False" in the 2nd cell. in the load dataset section
        - This may limits the use of the dataset, that is, the code for every algorithm has to be executed in a serialized fashion.
        - please note the explicitly provide the name and address of the dataset to be created, else this would overwrite the existing pickle objects.
        - additionally a save variable is created : and set to True if want to save figures and files while creating new dataset.
            - please note, this is not used later in the execution. additionally figure names are not associated with the name of the dataset implicitly, and are provided excternally, these are hardcoded, if the inputs are not changed, these may end up overwriting the exiting figure, please make a copy of exiting figures to a safe palce if this is not intended.
            
            
            
            
