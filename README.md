<!--
*** I got this amazing README from here: https://github.com/othneildrew/Best-README-Template 
-->

[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/PedroHCouto/UDACITY-ML-Engineer-Nanodegree-Project">
    <img src="Images/1_opening.jpg" width="700" height="300">
  </a>

  <h3 align="center">Stock Price Predictions of Brazilian commodity-based companies using AWS SageMaker</h3>


  <p align="center">
    Udacity Machine Engineer Nanodegree - Capstone Project
  </p>

<p align="center">
  <a href="https://github.com/PedroHCouto/UDACITY-ML-Engineer-Nanodegree-Project">
    <img src="https://miro.medium.com/max/1356/1*hWHfNVYS4B1dgB75bhUAXQ.png" width="150" height="75">
  </a>
    <br />
  </p>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">Table of Contents</h2></summary>
  <ol>
    <li><a href="#about-the-project">About The Project</a></li>  
    <li><a href="#built-with">Built With</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>


<!-- ABOUT THE PROJECT -->
## About The Project

In this problem the problem of Stock Price Prediction was approached in two steps:

1. Data Exploration in order to find out the most interesting company among the 5 commodity-based companies in Brazil.

2. Data preparation, feature engineering, model training and evaluation. 

All these steps were done in AWS SageMaker and used the AWS S3 to store the produced data and model artifacts.

The Jupyter Nootebook contains the code necessary to do the both steps mentioned above as well as explanations of the decision making process and how the code works.

A training algorithm for the LSTM model created with TensorFlow can be found in the train.py file. It basicly load the data, pre-process it, trains the model and save it in S3.


### Built With

* [Access to AWS plataform and its products like SageMaker and S3](https://aws.amazon.com/pt/sagemaker/) 
* [Jupyter Notebook](https://jupyter.org/try) 
* [yahooquery-API](https://github.com/dpguthrie/yahooquery)
* [json](https://docs.python.org/3/library/json.html)
* [numpy](https://numpy.org/)
* [pandas](https://pandas.pydata.org/)
* [datetime](https://docs.python.org/3/library/datetime.html)
* [os](https://docs.python.org/3/library/os.html)
* [matplotlib.pyplot](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.html)
* [plotly.graph_objects](https://plotly.com/python-api-reference/generated/plotly.graph_objects.Figure.html)
* [plotly.express](https://plotly.com/python/plotly-express/)
* [plotly.subplots.make_subplots](https://plotly.com/python/subplots/)
* [sklearn.preprocessing](https://scikit-learn.org/stable/modules/preprocessing.html)
* [sklearn.metrics](https://www.google.com/search?q=sklearn.metrics&oq=sklearn.metrics&aqs=chrome..69i57j0l5j69i60l2.1131j0j4&sourceid=chrome&ie=UTF-8)
* [sklearn.ensemble](https://scikit-learn.org/stable/modules/ensemble.html)
* [tensorflow](https://www.tensorflow.org/)
* [keras](https://keras.io/)


<!-- ROADMAP -->
## Roadmap

The project is guided by the following general outline:

a. Gathering the Data;   

b. Cleaning and Exploration;  

  - b.1. Checking missing values and a first look at the data;   
  - b.2. Checking the variation of the data over time with a line graph;   
  - b.3. Using the Moving Average to get another view of price variation;   
  - b.4. Visualization of Volumes over time;   
  - b.5. Daily Return;   
  - b.6. Risk Analysis;   
  - b.7. Correlations;   

c. Data Preparation;   

  - c.1. Train-Test Split;   
  - c.2. Upload the data to S3;   

d. Model Building;  

  - d.1. RandomForest Regressor;   
  - d.2. AWS DeepAR;   
  - d.3. LSTM Model with Tensor Flow;   

e. Results;   

f. Conclusion and Next Steps;    


<!-- CONTACT -->
## Contact

E-mail: pedrocouto39@gmail.com     
LinkedIn: https://www.linkedin.com/in/pdr-couto    
Kaggle: https://www.kaggle.com/pedrocouto39   
XING: https://www.xing.com/profile/Pedro_Couto8/cv     

Project Link: [https://github.com/PedroHCouto/UDACITY-ML-Engineer-Nanodegree-Project](https://github.com/PedroHCouto/UDACITY-ML-Engineer-Nanodegree-Project)


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/pdr-couto/
[product-screenshot]: images/screenshot.png
