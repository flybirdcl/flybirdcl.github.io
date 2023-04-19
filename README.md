# Predicting weather using LSTM neural networks


Project members: Cassidy Liu and Andrew Yu

By now, you should have a good idea of your project's motivations, scope, and potential results. Thus, you will now start filling in portions that will become your final report. For now, you only need to complete a rough draft of the introduction and related works sections (or combine them into a single narrative, whichever you find easier to write).

Create a new web-page with the following.

Copy over and then fill in your introduction outline and either weave-in the related works descriptions or create a new related works section. You will need to keep a references section at the end of the document (here is an example).
Write 400 to 800 words total (roughly one to two pages).
The key idea for the related works section is that it should be easy to read. It will no longer be a set of disjoint paragraphs. You should group together similar related studies and add transition sentences.

You will submit a link to your web-page on gradescope.

All of the information you provide is tentative, and I expect many groups to change their minds as projects evolve.


## Introduction


This introduction explores the use of neural networks in predicting weather in the future. It will be evaluating the benefits and costs of using neural networks as well as the feasability and other factors that need to be considered.

Part of what makes this project possible is the availability to detailed, real-time weather data. Modern data science and technology endeavors have allowed us to get accurate data from anywhere in the world. However, weather data is complex and expensive to obtain. There may be limited data available for training the neural network, which can impact its accuracy.

Predicting weather patterns are of interest for individuals, weather forecasters, and other weather-related concerns such as energy modeling and daylight analysis.  With the growth of machine learning, using neural networks to predict future weather patterns has become more popular. Weather predictions and gathering the predictions' relavent data is something that has long existed before using, so weather programs already have a variety of ways to predict weather. Our project will aim to mainly use historical weather data to predict future weather with recurrent neural networks.

One difficulty in predicting temperature in the long run is the addition of global warming into the equation. Global warming has also become a major concern for a lot of stakeholders of weather. Current weather prediction algorithms and equations may also be impacted with this addition as well.

Current meteorologists use numerical weather prediction models, which solve complex sets of mathematical equations based on the physics of air flow, and heat and moisture exchange, etc. This project focuses on implememnenting a LSTM (a type of RNN) with the use of historical weather data to make weather predictions.

Long Short-Term Memory (LSTM) is a type of recurrent neural network (RNN) that has been shown to excel at analyzing data sequentially. Since weather data is inherently sequential in nature, LSTM has become a popular approach for predicting weather patterns. LSTM models are capable of capturing the temporal dependencies in weather data, which makes them ideal for predicting complex weather phenomena. With the availability of vast amounts of historical weather data and recent advancements in deep learning techniques, LSTM models have become increasingly popular in weather forecasting. This technology has the potential to revolutionize how weather forecasts are made and can provide valuable insights for decision-making in various fields, including agriculture, aviation, and disaster management. In this context, this study will also explore the benefits and challenges associated with using LSTM for weather prediction and discuss the latest developments in this field.

One of challenges we anticipate having to face is having factors that affect the temperature that are not in our dataset. For example, if a volcano erupts or an urban city has a lot more pollution than normal, these may affect the temperature and will not show up in the dataset in a way that other weather phenomenons would.

## Ethical Sweep

Since weather forecasting is already really commonly done (with different methods), there aren't many more downsides to using neural networks to predict weather. Generally, there aren't many negative uses of weather data. Our model will only help further make different weather prediction services more accessible to people. Weather predictions are important on an individual level for planning and can also be used for resource management and agricultural applications.

Our project team originally had four people, but we cut down the team due to logistical. The current team only has two of us with similar ethnic backgrounds but different academic backgrounds (coming from different colleges and different professions), so that has helped us have more diverse discussions about how.

The addition of using neural networks also usually adds the question of data ethics. A lot of neural networks uses personal information and can cause issues with data privacy. Our web application will take location information that the user provides but does not save this information about the user. From the developers perspective, there will be no way of discerning which user has looked up what location's weather prediction. Data bias from this data set can be seen from what data was included and excluded. There are more physical factors that could factor into a place's temperature. For example, there is no data included that is relavent to greenhouse gases and the global warming impact on temperature. 

One misinterpretation of results could be that for a lot of users that aren't familiar with neural nets is that the decision process can seem like a black box and not backed on a real model that was trained by real historical data

## Methods

We utilize numpy and pandas to gather and scrape data from the following kaggle dataset: https://www.kaggle.com/datasets/selfishgene/historical-hourly-weather-data?select=humidity.csv. 

The data contains hourly weather data for 30 US & Canadian Cities and 6 Israeli Cities from 2012-2017. 

We specifically selected 4 files to use from the given kaggle link: humidity, pressure, temperature, and wind speed as we thought those were the main features that would most likely contribute to the temperature. 

We then preprocessed the data by taking the standard deviations of each of the features so the ranges of the value will be minimized to mainly between -3 and 3. And we made 80% of the data to be used to train the model, while the remaining 20% were to be used in the validation process. 

We then used the framework tensorflow and keras to create an LSTM (a type of RNN) in python to be trained on the preprocessed data. Specifically, the code defined a multi-step LSTM model using Keras and TensorFlow where it looked back and used data from 48 hours before to predict data 24 hours into the future.

The code was helped with the following tutorial https://machinelearningmastery.com/return-sequences-and-return-states-for-lstms-in-keras/ and can be found here: https://github.com/flybirdcl/WeatherPredict.

## Related Works

Kosandal's article is a good introduction in using recurrent neural networks (RNNs) in predicting weather (Kosandal, 2020). It runs through an example where it takes in a dataset containing historical temperature, wind speed, wind gust, etc. time series data and uses Python libraries to preprocess, train and run a model that will predict future temperatures.

An article discusses the uses of Artificial Neural Networks (ANNs) to predict weather data (Tran et al., 2021). The review shows that LSTMs and RNNs are probably effective tools to predict weather. Reviewed models include a variety of univariate and multivariate MLP (multilayer perceptron), FFNN (feed-forward neural network), FFBF (feed-forward back propagation), GRNN (generalized regression neural network), RBF ( radial basis function), CRNN (convlutional recurrent neural network), RNN, and LSTM models.

Another article explores the use of a simple recurrent neural network with convolutional filters, ConvLSTM, and an advanced generative network, the Stochastic Adversarial Video Prediction (SAVP) model (Gong et al., 2023). The model predicts hourly forecasts for places in Europe using 13 years of historical weather data in Europe.

A Washington Post article by Deaton explains new research that indicates how global warming will become a bigger factor in making weather predictions (Deaton, 2022). While right now, the global warming could just be a small source of error, this error could be compounded and cause bigger issues in weather models as time goes on. Additionally, the impact of global warming will only increase as greenhouse gas emissions continue to increase.

There are also many metereologists that study climatic trends using bottom-up physics-based general circulation and Earth system model approaches (Ise 2019). A study conducted by Ise and Oba detail a top-down approach by training a neural network and a huge dataset about historical global temperature. They were able to obtain 97.0% accuracy by using a LeNet convolutional neural network. The conclusion is that weather forecasting methods should include both a neural network component as well as a numerical method with a physics-based model.

## Discussion 
<img width="767" alt="image" src="https://user-images.githubusercontent.com/22489728/232861847-4b284a43-5662-49e4-8f1e-3116414d9b5f.png">

The final project presents a user interface that will give the predicted temperature at a given location (initially will only have a couple options). Currently, our team have a working model at 20% loss, and we are working on having it deployed. Data is evaluated with its accuracy to the actual reading after the predictions. The LSTM model we have is comparable to other atmospheric temperature neural networks; our team drew inspiration from many existing weather models as well as other LSTMs that have similar prediction models. The dataset for this model is a 2012-2017 historical weather dataset that includes field such as historical temperature, air pressure, humidity, city attributes, and wind speed and direction.

Below is one example of the prediction. We can see here that the model uses the past 48 hours of data, and predicts 24 hours into the future (shown on the x axis). We can see the predictions are similiar to the true values of the temperature at that time. 

![image](https://user-images.githubusercontent.com/22489728/232942080-ee6b6310-6df8-4369-b853-c900f84226d6.png)



## References

B. Gong, et al. “Temperature Forecasting by Deep Learning Methods.” Vol. 15, 2022, pp. 8931–8956. https://doi.org/10.5194/gmd-15-8931-2022. Accessed 15 Apr. 2023.

Deaton, Jeremy. “Climate Change Could Make Weather Harder to Predict.” The Washington Post, WP Company, 25 Jan. 2022, https://www.washingtonpost.com/weather/2022/01/25/climate-change-weather-unpredictable/. 

Ise T and Oba Y (2019) Forecasting Climatic Trends Using Neural Networks: An Experimental Study Using Global Historical Data. Front. Robot. AI 6:32. doi: 10.3389/frobt.2019.00032

Lheureux, Adil. “Weather Forecast Using LSTM Networks.” Paperspace Blog, Paperspace Blog, 13 Jan. 2023, https://blog.paperspace.com/weather-forecast-using-ltsm-networks/. 

Kosandal, Rohan. “Weather Forecasting with Recurrent Neural Networks.” Medium, Analytics Vidhya, 5 Jan. 2020, https://medium.com/analytics-vidhya/weather-forecasting-with-recurrent-neural-networks-1eaa057d70c3. 

Tran, Trang Thi Kieu, et al. “A Review of Neural Networks for Air Temperature Forecasting.” Water, vol. 13, no. 9, May 2021, p. 1294. Crossref, https://doi.org/10.3390/w13091294.

## Reflection
