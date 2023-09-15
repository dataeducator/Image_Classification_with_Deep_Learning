# Image Classification with Deep Learning
***
![Detecting Penumonia with Deep Learning](https://github.com/dataeducator/image_classification_with_deep_learning/assets/107881738/7259f2f8-e4f5-412b-bd02-a66aac2b6058)


# Introduction: 
#### __Disclaimer:__
This work is __intended solely for educational purposes__. The included business case and the results of the deep learning models should not be interpreted as medical advice and have not received endorsement or approval from any professional or medical organization.
The models and outcomes presented here are for illustrative purposes __only__ and should __not__ be utilized for making real-world decisions without consulting appropriate domain experts and medical professionals. Any actions taken based on the information in this notebook are at the user's own risk.
The author and contributors of this notebook disclaim any liability for the information's accuracy, completeness, or efficacy.
# Business Understanding:
* __Stakeholder__: Zephyr Health
* __Business Case__: I am a new data analyst on the Data Analytics team and have been tasked with building a model to classify whether a given patient has pneumonia given a chest x-ray.

According to a 2022 report (click [here](https://www.jhsph.edu/ivac/wp-content/uploads/2019/10/PDPR_2022.pdf) for full report) by Johns Hopkins over __700 thousand children under 5__ die from pneumonia each year.
# Objectives
The main objectives of this project are:

* Develop a robust and efficient system for early childhood pneumonia detection using a Convolutional Neural Network(CNN), which detects the presence of pneumonia with high precision.
* Generate a system that can be validated and deployed across various healthcare settings to reach underserved populations.

# Metrics for evaluation
Our task is a binary classification problem that uses chest x-ray images as input. Our model will predict whether the image depicts PNEUMONIA or a NORMAL chest x-ray. We will set the goal of __at least 90%  for the f-1 score__.
Our project will use the F1-score or the harmonic mean of recall and precision.

$$\
F1\text{-}Score = \frac{{2 \cdot \text{True Positive}}}{{2 \cdot \text{True Positive} + \text{False Positive} + \text{False Negative}}}
\$$

This formula represents the F1-score, which is a metric used to evaluate the performance of a binary classification model. It balances the trade-off between precision and recall.

Our model will be successful where:

$$\
F1\text{-}Score > .90
\$$

## Source of Data
The dataset used in this exploration is from this repository and can be found [here](https://data.mendeley.com/datasets/rscbjbr9sj/2)
-Citation: Kermany, Daniel; Zhang, Kang; Goldbaum, Michael (2018), “Large Dataset of Labeled Optical Coherence Tomography (OCT) and Chest X-Ray Images,” Mendeley Data, V3, doi: 10.17632/rscbjbr9sj.3


|   Image Type   |   Chest X-ray images                                      |
|:--------------:|:-------------------------------------------------------:|
|  Patient Age   |   1-5 years                                             |
|    Source      |   Pediatric Patients at Guangzhou Women and Children's Medical Center |
|   Location     |   Guangzhou, China during routine                        |
| Quality Control|   Initial screening + grading by 2 experts             |

|    Set    |    Class   | Number of Images |                                        
|---------:|----------|----------------|
|  Training |   Normal   |      1341        |
|  Training | Pneumonia  |      3875        |
|   Testing |   Normal   |       234        |
|   Testing | Pneumonia  |       390        |
| Validation|   Normal   |        8         |
| Validation| Pneumonia  |        8         |

![Class Distribution across sets](https://github.com/dataeducator/image_classification_with_deep_learning/assets/107881738/ac6c107e-a5f2-4343-b3d1-759b97dff743)

These images fall into two distinct categories:
- Pneumonia
- Normal


The data was biased, with the PNEUMONIA class having more than twice the number of images as the NORMAL class, so the PNEUMONIA class was shortened to a random selection of images equal to the number of NORMAL images in the training set.

![Class Distribution rebalanced training set](https://github.com/dataeducator/image_classification_with_deep_learning/assets/107881738/dda7cbf1-b39f-45c4-bcfa-f59bc742fee7)


### Exploration

![Pixel Intensities of Sample Images](https://github.com/dataeducator/image_classification_with_deep_learning/assets/107881738/b0b11796-c5b4-4afd-a620-7402e6830588)


## Modeling
In this project, I will use the __OSEMiN__ pipeline to:

- Obtain → Import the data.
- Scrub → Manage the datatypes and resolve missing data or duplicates.
- Explore → Identify patterns within the relationships between variables in the data.
- Model → Create a set of predictive models.
- iNterpret → Identify insights and create visualizations of findings.

For our model, we could prioritize:

- accuracy - the proportion of correctly predicted labels from all of the samples in the testing dataset.
- precision - measures the model's accuracy in predicting true positives as a proportion of all positives.
- recall- measures the model's ability to measure all positive instances correctly.
- f1-score - the harmonic mean of precision and recall, used when we want to consider both identifying true positives and minimizing false negatives.

Our best model uses sequential, convolutional, dense, and dropout layers and is illustrated below:
![Model](https://github.com/dataeducator/image_classification_with_deep_learning/assets/107881738/c09fbb0b-835b-4e59-8a05-8d1fd41183a6)
| Model                   | Precision (NORMAL) | Recall (NORMAL) | F1-Score (NORMAL) | Precision (PNEUMONIA) | Recall (PNEUMONIA) | F1-Score (PNEUMONIA) | Accuracy | 
|-------------------------|--------------------|----------------|------------------|---------------------|--------------------|---------------------|----------|
| Revised CNN             | 0.94               | 0.76           | 0.84             | 0.87                | 0.97               | 0.92                | 0.89     |
| Baseline CNN            | 0.40               | 0.19           | 0.26             | 0.63                | 0.83               | 0.72                | 0.59     |


## Insights
The Confusion Matrix for our Test set is shown here:
![Confusion Matrix best model](https://github.com/dataeducator/image_classification_with_deep_learning/assets/107881738/aec157e2-2d7b-4257-828b-6df88e9ed755)

We also compare the F1-Scores of the different models we tested out as we attempted this proof of concept task:
![F1-scores different models](https://github.com/dataeducator/image_classification_with_deep_learning/assets/107881738/e79aac2b-8736-469e-a703-1e673746a2cd)

We also experimented with LIME in an attempt to make what our model identifies as important features visible. Here is an example of an image, it's true classification label,
it's a predicted classification label and a segmented image that highlights "features" of importance to our current best model.

![Lime Output](https://github.com/dataeducator/image_classification_with_deep_learning/assets/107881738/8de0095d-c294-4af2-95fd-5003b39e3db5)

## Recommendations:
*Expert-evaluated data for Model Enhancement
Utilizing images that have been expert-evaluated is crucial for improving the accuracy and performance of our model. This can be achieved through the following steps:
- **Collaboration with Radiology Experts**: Establish partnerships with radiologists and other medical professionals to evaluate X-ray images. Their expertise will contribute to a high-quality annotated dataset.
- **Continuous Feedback Loop**: Implement a feedback mechanism to incorporate expert evaluations into the training pipeline, ensuring the model learns from expert insights.
* Optimal Scanner Placements
To maximize the effectiveness of our Pneumonia detection system, it is recommended to strategically deploy X-ray scanners and computer systems with our model in the following locations to run a pilot to collect more expert verifiable data:
- **Pediatric Wards and Clinics**: Ensure accessibility to children in healthcare facilities where pneumonia cases are most frequently diagnosed and treated.
- **High-Risk Areas and Communities**: Identify regions with elevated incidences of childhood pneumonia and establish scanning facilities near these communities.

## Future Work: 
Please review my full analysis in [my Jupyter notebook]( ) or ([my presentation]( )).
Feel free to contact me __Tenicka Norwood__ at tenicka.norwood@gmail.com if you have any more questions.

# Repository Structure
***
<pre>
   .
   └──image_classification_with_deep_learning/
      ├── README.md                                            Overview for project reviewers  
      ├── image_classification_with_deep_learning.ipynb        Documentation of Full Analysis in Jupyter Notebook
      ├── presentation.pdf                                     PDF version of Full Analysis shown in a slide deck
      ├── notebook.pdf                                         PDF version of Full Analysis shown in Jupyter notebook
      ├── setup.yml                                            Includes instructions to obtain dataset
      └── .gitignore                                           Specifies intentionally untracked files
