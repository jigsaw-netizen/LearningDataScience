# Motivation 
I have been learning data science on my own for a while now and thouht it was a shame I had no repo to show off my work so .... I made a repo ! I didn't use this repo while i was working so i'm grouping some of my earlier projects under one repo (not what i owuld do for a project actually using git)

# Content

## Andrew NG machine learning course

I'm not going to upload the code for these (computer died, long story). It's really a bible to get started !
Did the full MOOC online and all associated exercises which involve coding many of the fundamental algorithms (svm, backpropagation, regression, ..) by hand

## Detecting solar panels
The purpose is to be able to identify solar panels in satellite images. This has many applications, the one i had in mind was commercial prospection and automatically producing quotes for home insurance. An other application would be tracking solar capacity of a region over time.
This entails a few things :
- I have to link it with the land register
- I have to get satellite images
- I have to identify solar panels in an image
- I have to know to surface of the solar panel

I tried to find an annotated dataset to train my network, found many aerial pictures with the solar panels tagged by polygons.

The dataset was extremely skewed (only a very small proportion of the photos were solar panels) so i iterated over my polygons (i.e. solar panels) and cropped the image around them. These cropped images, with some added negative examples, would make up my training data.

To create my target variable I iterated over my polygons and created a mask (numpy array with ones inside the polygon and 0 outside).
Since NN take inputs of constant size, i used a sliding window over both the cropped image and the corresponding mask to create my xi and yi's.

I tried many iterations of neural network architectures (simple, convolutional, ....) as well as meta parameters (window size, stride, ....) to get the best results possible (metric hard to choose without actual business case, in case of marketing F1 seems alright, for insurance quotes i wanted a good recall (since they make a decent amount of money per client, i assumed they could manually filter out false positives)

My takeaways :
- write macro-parameters as variables to be able to change them easily (fullcaps to recognise them)
- Do not use libraries without looking into them (i had no idea what my polygons were made of, i lost more time undersanding bugs than i would have coding my own polygons)
- Have a standard way of naming variables and stick to it
- Having an actual business expert seems interesting, must try to find one for a project (if you are one, contact me =)

## ASHRAE Energy predictor
The purpose of this competition was to predict energy consumption of buildings. You might notice a trend : i like projects that could help with real socieatal issues like energy consumption (my intuition tells me we're gonna need some good data science to handle renewables and smartgrids)

The most interesting part of this project was the EDA, the data had a lot of noise, some specific missing values, etc.. which had to be handled properly before being able to use the data to train anything.

My takeaways :
- EDA is challenging and is necessary to be able to clean data well
- There is a lot of work involved before training 
- Data exploration is more fun and involves a lot more thinking than i would have thought
- Seaborn looks better than pyplot

## Forest types
Todo : write this part
