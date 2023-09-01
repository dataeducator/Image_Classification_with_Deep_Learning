# Image Classification with Deep Learning
***
[Source: CDC on Unsplash]![cdc-SrHKQxGuuqQ-unsplash](https://github.com/dataeducator/image_classification_with_deep_learning/assets/107881738/fc6707d7-9dcf-49c4-915f-f504331c79c0)



# Business Understanding:
* __Stakeholder__: Zephyr Health
* __Business Case__: I am a new data analyst on the Data Analytics team and have been tasked with building a model to classify whether a given patient has pneumonia given a chest x-ray.

# Overview
The main objectives of this project are:

* Develop a robust and efficient system for early childhood pneumonia detection using a Convolutional Neural Network(CNN), which detects the presence of pneumonia with high precision.
* Generate a system that can be validated and deployed across various healthcare settings to reach underserved populations.

# Data Understanding and Analysis
***
In this project, I will use the OSEMiN pipeline to:

* Obtain → Import the data.
* Scrub → Manage the datatypes and resolve missing data or duplicates.
* Explore → Identify patterns within the relationships between variables in the data.
* Model → Create a set of predictive models.
* iNterpret → Identify insights and create visualizations of findings.

Metrics
We will prioritize precision in this project over accuracy. We will also aim to balance recall (sensitivity) and high precision (specificity). With these objectives in mind, we aim to reduce the number of false positives and increase the model's ability to correctly identify patients with pneumonia. In this context, false positives could lead to unnecessary treatment or interventions.

* __True positives__ are the cases when a model predicts positive instances correctly.
Ex. patients predicted to have PNEUMONIA and do have PNEUMONIA.

* __False positives__ are the cases when a model predicts positive instances incorrectly. Ex. patients are predicted to have PNEUMONIA, but the chest scan label is NORMAL.

* ___False negatives__ are the cases when a model mispredicts negative instances. Ex. patients predicted to have NORMAL chest scans and do have PNEUMONIA.



## Source of Data
The Mendeley repository contains a dataset for evaluating machine learning techniques. The dataset used in this exploration is from this repository and can be found [here]((https://data.mendeley.com/datasets/rscbjbr9sj/2).)]
-Citation: Kermany, Daniel; Zhang, Kang; Goldbaum, Michael (2018), “Large Dataset of Labeled Optical Coherence Tomography (OCT) and Chest X-Ray Images,” Mendeley Data, V3, doi: 10.17632/rscbjbr9sj.3

Contained within this dataset are numerous validated OCT and Chest X-ray images, which have been meticulously described and analyzed in the publication titled "Identifying Medical Diagnoses and Treatable Diseases by Image-Based Deep Learning." These images have been categorized into distinct training and testing sets, each involving separate patients. Organized into four directories—CNV, DME, DRUSEN, and NORMAL—the images are appropriately labeled using a format of (disease)-(randomized patient ID)-(image number within the patient).


## Description of Data
***
The dataset is organized into three main folders: "train," "test," and "val." You will find subfolders within these folders corresponding to each image category: "Pneumonia" and "Normal." This dataset consists of 5,863 JPEG format X-ray images. 
The chest X-ray images, captured in the anterior-posterior view, were meticulously chosen from retrospective cohorts of pediatric patients aged one to five years old. These patients were affiliated with the Guangzhou Women and Children’s Medical Center in Guangzhou. The patients' regular clinical care included all chest X-ray imaging procedures.

An initial quality control screening was performed to ensure the quality of the analysis of chest X-ray images. This screening involved the removal of scans that were of low quality or deemed unreadable. Following this step, the images underwent diagnosis assessment. Two expert physicians assessed and graded the diagnoses associated with the images before they were deemed suitable for training the AI system. Additionally, a third expert reviewed the evaluation set to account for any potential grading discrepancies.

These images fall into two distinct categories:
- Pneumonia
- Normal

First, I needed to import relevant libraries and packages to determine answers to my guiding questions.

* <code>pandas</code>: a data analysis and manipulation library which allows for flexible reading, writing, and reshaping of data
* <code>numpy</code>: a key library that brings the computational power of languages like C to Python
* <code>matplotlib</code>: a comprehensive visualization library
* <code>seaborn</code>: a data visualization library based on matplotlib
* <code>statsmodels</code>: a library used to understand statistical relationships between variables, often used in economics.
* <code>sklearn</code>: a machine learning library for data processing and modeling.
* <code>keras</code>:

## Modeling

### Obtain
__ObtainData Class Description__
The <code>ObtainData</code> class is a utility class designed to retrieve Google Drive data. This class provides an approach to mount Google Drive, verify the existence of a specified dataset folder, and extract its contents if necessary.

__Features:__

* Mounts Google Drive to the Colab environment, providing users access to the files stored in their Google Drive.
* Prompts the user to input the location of the dataset folder within their Google Drive
* Checks to see if the specified dataset folder exists and provides feedback to the user.
* If the dataset folder exists, this class provides a convenient way to access the dataset files.

__Usage:__

* Create an instance of the ObtainData class.
* Invoke the get_dataset_location() method to prompt the user to input the location of the dataset folder in their Google Drive.
* The class automatically verifies the existence of the specified folder and provides feedback accordingly.
* The dataset files can then be accessed and processed as needed.

### Scrub


### Explore



### Visualization 



### Model


### Evaluation


### iNterpret

## Conclusion

## Insights
Based on the information from the confusion matrices and feature analysis, we recommend the following:



 


# Future Work
* Explore applying...
* Extending the analysis to include... 
* Identifying...

Please review my full analysis in [my Jupyter notebook]( ) or ([my presentation]( )).
You may contact me __Tenicka Norwood__ at tenicka.norwood@gmail.com if you have additional questions.

# Repository Structure
***
<pre>
   .
   └──image_classification_with_deep_learning/
      ├── README.md                                            Overview for project reviewers  
      ├── image_classification_with_deep_learning.ipynb        Documentation of Full Analysis in Jupyter Notebook
      ├── presentation.pdf                                     PDF version of Full Analysis shown in a slide deck
      ├── notebook.pdf                                         PDF version of Full Analysis shown in Jupyter notebook
      ├── Images/                                              Includes images generated from Python code and sourced externally
      └── .gitignore                                           Specifies intentionally untracked files
