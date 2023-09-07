# Image Classification with Deep Learning
***
![Detecting Penumonia with Deep Learning](https://github.com/dataeducator/image_classification_with_deep_learning/assets/107881738/7259f2f8-e4f5-412b-bd02-a66aac2b6058)


# Introduction: 
#### __Disclaimer:__
This work is __intended solely for educational purposes__. The included business case and the results of the deep learning models should not be interpreted as medical advice, and have not received endorsement or approval from any professional or medical organization.
The models and outcomes presented here are for illustrative purposes __only__ and should __not__ be be utilized for making real-world decisions without consulting appropriate domain experts and medical professionals. Any actions taken based on the information in this notebook are at the user's own risk.
The author and contributors off this noteboo disclaim any liability for the accuracy, completeness, or efficacy of the information provided.
# Business Understanding:
* __Stakeholder__: Zephyr Health
* __Business Case__: I am a new data analyst on the Data Analytics team and have been tasked with building a model to classify whether a given patient has pneumonia given a chest x-ray.

According to a 2022 report (click [here](https://www.jhsph.edu/ivac/wp-content/uploads/2019/10/PDPR_2022.pdf) for full report) by Johns Hopkins over __700 thousand children under 5__ die from pneumonia each year.
# Objectives
The main objectives of this project are:

* Develop a robust and efficient system for early childhood pneumonia detection using a Convolutional Neural Network(CNN), which detects the presence of pneumonia with high precision.
* Generate a system that can be validated and deployed across various healthcare settings to reach underserved populations.

# Metrics for evaluation
Our task is in essence a binary classification problem that uses chest x-ray images as input. Our model will provide a prediction of whether the images is one that depicts PNEUMONIA or depicts a NORMAL chest x-ray. We will set the goal of __at least 90%  for the f-1 score__ .
For our project we will use F1-score or the harmonic mean of recall and precision.

\begin{gathered}
F1-Score  = \frac{2 \cdot True\ Positive}{2 \cdot True\ Positive + False\ Positive + False\ Negative}
\end{gathered}

Our model will be successful where:

\begin{gathered}
F1-Score  >= .90
\end{gathered}

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
![Class Distribution across sets](https://github.com/dataeducator/image_classification_with_deep_learning/assets/107881738/ac6c107e-a5f2-4343-b3d1-759b97dff743)

The data was biased with the PNEUMONIA class having more than twice the number of images as the NORMAL class, so the PNEUMONIA class was shortened to a random selection of images equal to the number of NORMAL images in the training set.
![Class Distribution rebalanced training set](https://github.com/dataeducator/image_classification_with_deep_learning/assets/107881738/dda7cbf1-b39f-45c4-bcfa-f59bc742fee7)

## Modeling


### Visualizations 

![Pixel Intensities of Sample Images](https://github.com/dataeducator/image_classification_with_deep_learning/assets/107881738/b0b11796-c5b4-4afd-a620-7402e6830588)


## Conclusion


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
      ├── setup.yml                                            Includes instructions to obtain dataset that corresponds to this repository
      └── .gitignore                                           Specifies intentionally untracked files
