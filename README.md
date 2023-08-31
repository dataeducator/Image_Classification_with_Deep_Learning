# Image Classification with Deep Learning
***
[Source: CDC on Unsplash]![cdc-SrHKQxGuuqQ-unsplash](https://github.com/dataeducator/image_classification_with_deep_learning/assets/107881738/fc6707d7-9dcf-49c4-915f-f504331c79c0)



# Business Understanding:
* __Stakeholder__: Zephyr Health
* __Business Case__: I am a new data analyst on the Data Analytics team and have been tasked with building a model that can classify whether a given patient has pneumonia given a chest x-ray.

# Overview
The aim is to create a dependable model using 

# Data Understanding and Analysis
***
In this project, I will use the OSEMiN pipeline to:

* Obtain → Import the data.
* Scrub → Manage the datatypes, and resolve missing data or duplicates.
* Explore → Identify patterns within the relationships between variables in the data.
* Model → Create a set of predictive models.
* iNterpret → Identify insights and create visualizations of findings.

We will prioritize ______ in this project over ______. By prioritizing ______, we aim to reduce the number of ________ and increase the model's ability to correctly_________. Minimizing the number of _______ will help to ensure that _____________________________________________________________.

* True positives are the cases when a model predicts positive instances correctly.
    - Ex. 
* False negatives are the cases when a model mispredicts negative instances.
    - Ex. 

## Source of Data
The Mendeley repository contains a dataset for evaluating machine learning techniques. The dataset used in this exploration is from this repository and can be found [here]((https://data.mendeley.com/datasets/rscbjbr9sj/2).)]
-Citation: Kermany, Daniel; Zhang, Kang; Goldbaum, Michael (2018), “Large Dataset of Labeled Optical Coherence Tomography (OCT) and Chest X-Ray Images”, Mendeley Data, V3, doi: 10.17632/rscbjbr9sj.3

Contained within this dataset are numerous validated OCT and Chest X-Ray images, which have been meticulously described and analyzed in the publication titled "Identifying Medical Diagnoses and Treatable Diseases by Image-Based Deep Learning." These images have been categorized into distinct training and testing sets, each involving separate patients. Organized into four directories—CNV, DME, DRUSEN, and NORMAL—the images are appropriately labeled using a format of (disease)-(randomized patient ID)-(image number within patient).


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


### Scrub


### Explore


###  Question 1: 
***


### Visualization for Question 1



### Question 2:
***


### Visualization for Question 2



### Question 3:  
***


### Visualization for Question 3



### Model


### Evaluation


### iNterpret

## Conclusion

## Insights
Based on the information from the confusion matrices and feature analysis, we recommend the following:


### Insight 1: Curricular Units in 2nd Semester Matter
 

### Insight 2: Monitoring Tuition Fee Payments is Pivotal 

### Insight 3: Evaluations and Grades are Crucial
 


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
