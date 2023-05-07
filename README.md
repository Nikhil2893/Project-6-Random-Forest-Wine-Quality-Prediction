# Project-6-Random-Forest-Wine-Quality-Prediction
Random Forest Wine Quality Prediction

# About Dataset
##Context
The two datasets are related to red and white variants of the Portuguese "Vinho Verde" wine. For more details, consult the reference [Cortez et al., 2009]. Due to privacy and logistic issues, only physicochemical (inputs) and sensory (the output) variables are available (e.g. there is no data about grape types, wine brand, wine selling price, etc.).

These datasets can be viewed as classification or regression tasks. The classes are ordered and not balanced (e.g. there are much more normal wines than excellent or poor ones).

This dataset is also available from the UCI machine learning repository, https://archive.ics.uci.edu/ml/datasets/wine+quality , I just shared it to kaggle for convenience. (If I am mistaken and the public license type disallowed me from doing so, I will take this down if requested.)

Content
For more information, read [Cortez et al., 2009].

Input variables (based on physicochemical tests):

1 - fixed acidity

2 - volatile acidity

3 - citric acid

4 - residual sugar

5 - chlorides

6 - free sulfur dioxide

7 - total sulfur dioxide

8 - density

9 - pH

10 - sulphates

11 - alcohol

Output variable (based on sensory data):

12 - quality (score between 0 and 10)

Tips
What might be an interesting thing to do, is aside from using regression modelling, is to set an arbitrary cutoff for your dependent variable (wine quality) at e.g. 7 or higher getting classified as 'good/1' and the remainder as 'not good/0'.
This allows you to practice with hyper parameter tuning on e.g. decision tree algorithms looking at the ROC curve and the AUC value.
Without doing any kind of feature engineering or overfitting you should be able to get an AUC of .88 (without even using random forest algorithm)

KNIME is a great tool (GUI) that can be used for this.

1 - File Reader (for csv) to linear correlation node and to interactive histogram for basic EDA.

2- File Reader to 'Rule Engine Node' to turn the 10 point scale to dichtome variable (good wine and rest), the code to put in the rule engine is something like this:

$quality$ > 6.5 => "good"
TRUE => "bad"

3- Rule Engine Node output to input of Column Filter node to filter out your original 10point feature (this prevent leaking)

4- Column Filter Node output to input of Partitioning Node (your standard train/tes split, e.g. 75%/25%, choose 'random' or 'stratified')

5- Partitioning Node train data split output to input of Train data split to input Decision Tree Learner node and

6- Partitioning Node test data split output to input Decision Tree predictor Node

7- Decision Tree learner Node output to input Decision Tree Node input

8- Decision Tree output to input ROC Node.. (here you can evaluate your model base on AUC value)
Inspiration
Use machine learning to determine which physiochemical properties make a wine 'good'!

Acknowledgements
This dataset is also available from the UCI machine learning repository, https://archive.ics.uci.edu/ml/datasets/wine+quality , I just shared it to kaggle for convenience. (I am mistaken and the public license type disallowed me from doing so, I will take this down at first request. I am not the owner of this dataset.

Please include this citation if you plan to use this database: P. Cortez, A. Cerdeira, F. Almeida, T. Matos and J. Reis. Modeling wine preferences by data mining from physicochemical properties. In Decision Support Systems, Elsevier, 47(4):547-553, 2009.


1. Importing Dependencies

![001](https://user-images.githubusercontent.com/114944969/229364273-3df063f0-ccfa-4da1-a6c8-aa5cca28ab37.jpg)

2. Importing dataset and EDA

![002](https://user-images.githubusercontent.com/114944969/229364332-48731766-b298-4cdb-aa7c-9743c6d77bd3.jpg)

![003](https://user-images.githubusercontent.com/114944969/229364373-45d9b211-953a-4278-bd98-4d62dd8dd6bb.jpg)

![004](https://user-images.githubusercontent.com/114944969/229364459-b85c351d-3260-4e0c-8d37-fbdfdd5e44ed.jpg)


3. Splitting data into train and test

4. Model Training with Random Forest Classifier

![005](https://user-images.githubusercontent.com/114944969/229364531-60156e00-8848-421a-8528-c64f618d181e.jpg)

5. Model Evaluation 

![6](https://user-images.githubusercontent.com/114944969/229364573-3c0a005f-c737-4476-b0eb-e116e749bc06.jpg)

Model achieved accuracy of 100% on training data and 90% on test data

6. Build Predictive System
![7](https://user-images.githubusercontent.com/114944969/229364650-c1d2ccda-e957-47fb-8ee6-2ea20ac651e2.jpg)


## Acknowledgements

I have followed the YouTube tutorial of "Siddardhan"

[Click for Video Link](https://www.youtube.com/watch?v=CBxJuwrGrc4&list=PLfFghEzKVmjvuSA67LszN1dZ-Dd_pkus6&index=6)

## Authors

- [Nikhil Wakode](https://github.com/Nikhil2893)

## Documentation

[Click the link to study Random Forest Classifier](https://www.geeksforgeeks.org/random-forest-classifier-using-scikit-learn/)


## Installation

[No Installation is required to run the code as No UI app is created in this one. The predictive system can run on Google Colaboratory.
Please open the **"Project-6-Random-Forest-Wine-Quality-Prediction.ipynb"** file with the help of Google Colaboratory]
(https://colab.research.google.com/)
    
## Lessons Learned

This is classification problem which could be solved by above mentioned steps in Introduction.

## 🚀 About Me
I'm a DATA SCIENCE enthusiast...

# Hi, I'm Nikhil! 👋

## 🛠 Skills
Machine Learning, Deep Learning - ANN,CNN,RNN, Computer Vision,NLP,Statistics,Strategic Planning, Urban Planning, Python, PostgreSQL, PowerBI, Tableau, Excel, GIS

## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://nikhil2893.github.io/Portfoilio_Nikhil/)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/nikhil-wakode/
)

## Feedback

If you have any feedback, please reach out to us at 
nikhilwakode2893@gmail.com
