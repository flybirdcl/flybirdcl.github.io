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

## Methods

You should now have a good idea of how you will complete your project. Add a “methods” section to your report web-page, which already includes a draft of your introduction and related works sections.

Revise your introduction and related works.
Add an outline of your methods section with a five to ten sentence outline while incorporating relevant information from your project updates. Relevant information includes the
software you are using,
datasets you are using,
tools you will use for analysis,
possible pitfalls,
etc.

We utilize numpy and pandas to gather and scrape data from the following kaggle dataset: https://www.kaggle.com/datasets/selfishgene/historical-hourly-weather-data?select=humidity.csv. We specifically selected 4 files to use from the given kaggle link: humidity, pressure, temperature, and wind speed. We then preprocessed the data by taking the standard deviations of each column so the ranges of the value will be minimized to mainly between -3 and 3. nd we made 80% of the dat to be used to train the model, while the remaining 20% were to be used in the validation process. We then used the framework tensorflow and keras to create an LSTM (a type of RNN) in python to be trained on the kaggle dataset we selected. We then planned on using a simple web application to deploy and display our trained model and allow users to interact with it. 

## Related Works

Create a new web-page with the following information.

At least five related works (research, blog posts, videos, books, etc.).
At least two should be research articles
For each work, you should provide a one to three sentence summary.
With the related works, try to answer the question: what is the state-of-the-art in the domain of your project?

This is similar to an annotated bibliography, but I am not expecting you to write more than a few sentences for each entry.

Final reports will require more than one research articles, and you should plan on collecting/skimming additional related works throughout the semester.

You will submit a link to your web-page on gradescope.

## Discussion 

Although you probably will not have final results at this time, you should start outlining your discussion/results. Add a “discussion” section to your report web-page.

Revise your current text.
Add an outline of your discussion/results section.
Five to ten sentence outline
Think about:
what data you will present,
how you will interpret/evaluate your data,
how your work compare to others, and
how will you prove your point (support your claims).
You can also include explanations of important concepts that you have learned/implemented. Feel free to do this in a tutorial style.

For projects that are focused on an application or ethics discussion, you can tweak your discussion outline to match your topic.

Here is an example (and I've added comments in parentheses that would not be part of the submission):

## References

B. Gong, et al. “Temperature Forecasting by Deep Learning Methods.” Vol. 15, 2022, pp. 8931–8956. https://doi.org/10.5194/gmd-15-8931-2022. Accessed 15 Apr. 2023.

Kosandal, Rohan. “Weather Forecasting with Recurrent Neural Networks.” Medium, Analytics Vidhya, 5 Jan. 2020, https://medium.com/analytics-vidhya/weather-forecasting-with-recurrent-neural-networks-1eaa057d70c3. 

Tran, Trang Thi Kieu, et al. “A Review of Neural Networks for Air Temperature Forecasting.” Water, vol. 13, no. 9, May 2021, p. 1294. Crossref, https://doi.org/10.3390/w13091294.

## Reflection
