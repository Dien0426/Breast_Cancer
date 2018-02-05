# Readme: Breast-Cancer-Project

## Data set information:
Breast-cancer data set was collected periodically by Dr. Wolberg who works at University of Wisconsin Hospitals. This data set includes 10 different features which are from the patient’s clinical report for both benign and malignant status. More information of the data set can be found [here](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+\(Original\)). I will just show a quick summary here.
1. Sample code number: id number 
2. Clump Thickness: 1 - 10 
3. Uniformity of Cell Size: 1 - 10 
4. Uniformity of Cell Shape: 1 - 10 
5. Marginal Adhesion: 1 - 10 
6. Single Epithelial Cell Size: 1 - 10 
7. Bare Nuclei: 1 - 10 
8. Bland Chromatin: 1 - 10 
9. Normal Nucleoli: 1 - 10 
10. Mitoses: 1 - 10 
11. Class: (2 for benign, 4 for malignant)

## Problem statements:
* Goal: Use the breast-cancer data set to build a model which can predict whether a patient’s tumor is benign or malignant. Then a doctor can proceed to have further test or treatment on the patient.
* Based on the statistics report about 40.000 women die of breast cancer per year in United States. However, this cancer can be treated very effectively if detected in its earlier stages. This problem can help improve the diagnostic accuracy on breast-cancer patients. 

* Attention needs to be paid to false positive (FP) and false negative (FN) cases of the model prediction. 
* False Positive: it means that the tumor is benign but predicted to be malignant. This case will require more tests and treatments, meaning that it would be wasteful in terms of resource but not patient’s life.
* False Negative: it means that tumor is malignant but predicted as benign. Such patients will not get the early treatment and tumor has time to grow to more serious stages and it is more dangerous for patient’s life.

## Files:
* Readme: You are reading this file
* breast-cancer-wisconsin.data: data file. You can get it directly from [this link](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+\(Original\))
* Breast\_cancer\_visualize\_model.ipynb: Python jupyter notebook file for visualization and modeling data.

## Requirements to run this project: 
1. Numpy
2. Pandas
3. Matplotlib
4. SKlearn
5. Seaborn

## Summary/Discussion
In this project, after processing and visualizing data (please see the ipynb file for detail), I used the Adaboost classifier and KNeighbors algorithms to classify the status of the breast tumor. I used Isomap to reduce the dimension of input features and gridsearchCV to tune the hyperparameters.
* The accuracies of both algorithms are about 96%. But I noticed that this data set is not balanced so accuracy is not the best quantity to evaluate the model performance. The confusion-matrix, precision and recall will be more relevant to evaluate the model. 
* The KNeighbors gives a better False Negative. The recall of “malignant” increases from 95% (Adaboosted) to 97% (KNeighbors). It means that more malignant status is predicted correctly. 
* Both models perform reasonably well in terms of precision and recall, but we still have room to improve the model:
  * Try other algorithms to see if any other gives better performance
  * Deal with the imbalance in data
  * Optimize the feature selection
