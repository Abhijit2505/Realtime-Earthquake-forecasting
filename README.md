# Realtime Earthquake Predictor application 

A realtime earthquake predictor web app with google maps API, that forecasts earthquake possible epicenters and places in window of next 7 days. This project is part of Udacity Nanodegree Data science capstone project. 

![web-app](https://github.com/aditya-167/Realtime-Earthquake-forecasting/blob/master/Images/application.jpg)

Web app link : [http://srichaditya3098.pythonanywhere.com/](http://srichaditya3098.pythonanywhere.com/)
## Contents

   * Project Overview
   * Problem Statement and approach to solution
   * Metrics 
   * Exploratory Data Analysis and Data processing
   * Model implementation
   * Improvement and evaluation
   * Prediction and web application
   * Improvement and conclusion
   * Deployment web app
   * Instructions to run the project
   * acknowledgement

### Project Overview
Countless dollars and entire scientific careers have been dedicated to predicting where and when the next big earthquake will strike. But unlike weather forecasting, which has significantly improved with the use of better satellites and more powerful mathematical models, earthquake prediction has been marred by repeated failure due to highly uncertain conditions of earth and its surroundings.
Now, with the help of artificial intelligence, a growing number of scientists say changes in the way they can analyze massive amounts of seismic data can help them better understand earthquakes, anticipate how they will behave, and provide quicker and more accurate early warnings. This helps in hazzard assessments for many builders and real estate business for infrastructure planning from business perspective. Also many lives can be saved through early warning. This project aims a simple solution to above problem by predicting or forecasting likely places to have earthquake in next 7 days. For user-friendly part, this project has a web application that extracts live data updated every minute by USGS.gov and predicts next likely place world wide to get hit by an earthquake, hence a realtime solution is provided.

### Problem Statement and approach to solution
Anticipating seismic tremors is a pivotal issue in Earth science because of their overwhelming and huge scope outcomes. The goal of this project is to predict where likely in the world and on what dates the earthquake will happen. Application and impact of the project​ includes potential to improve earthquake hazard assessments that could spare lives and billions of dollars in infrastructure and planning. Given geological locations, magnitude and other factors in dataset from https://earthquake.usgs.gov/earthquakes/feed/v1.0/csv.php for 30 days past which is updated every minute, we predict or forecast 7 days time in future that is yet to come, the places where quake would likely happen. The web app uses Google maps api to predict places where earthquake might occur.

### Metrics

The problem addressed above is about binary classification, `Earthquake occur = 1` and `Earthquake not occur = 0` and with these prediction we try to locate co-cordinates corrosponding to the predictions and display it on the google maps api web app. More suitable metrics for binary clsssification problems are **ROC (Reciever operator characteristics), AUC (Area Under Curve), Confusion matrix for Precision, recall, accuracy and sensitivity**. One important thing about choosing metrics and model is what exactly we need from predictions and what not. To be precise, we need to **minimize or get less False negative predictions** since we dont want our model to predict as `0` or `no earthquake occured` at particular location when in reality it had actually happend as this is because it is more dangerous than the prediction case in which prediction is `true/1` or `earthquake occured` but in reality it did not because its always **better safe than sorry!!!**. Hence apart from `roc_auc score`, I have considered `Recall` as well for evaluation and model selection with `higher auc_roc score and recall`, where `recall = (TP/TP+FN)`
