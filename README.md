# Inexplicable Podiatry
## The Search for Sasquatch and his Alien Friends
Daron Marino, Samuel Narvaez, Hanzhi Guo, Joseph Aylsworth
### EDA
Given the nature of natural language processing, the data required a substantial amount of processing and took up the greatest portion of the day. At the outset, we each started working independently on functions to handle abberant values and create a workable input. After some incremental progress, Daron created a DeepNote for everyone to centralize their efforts. The result was a single function that was able to extract the sightings and their respective attributes, i.e. location, time,  eyewitness account, and even shape! 

### Observing Visualized Data
While still text-based, the processing enabled typical EDA approaches, like visualizing bar plots to identify trends in the data. There's nothing revelatory here, but it is still the easiest and fastest way to identify trends worth investigation!

|![UFOYearOccurences](https://user-images.githubusercontent.com/43886791/112696566-17a4b780-8e54-11eb-9556-1baa2bfc3ac4.png)|
|:--:|
|Proof of concept: Cleaning up the smaller dataset makes these graphs possible|
|![UFOTop10States](https://user-images.githubusercontent.com/43886791/112698025-c77b2480-8e56-11eb-9cf9-947a31743b0a.png)|
|*Watch your head if you live in California, I guess*|

Since we knew the processing worked on the smaller dataset, we processing through the thousands and thousands of observations. 

|![UFOShapeFormatted](https://user-images.githubusercontent.com/43886791/112697159-090ad000-8e55-11eb-8cf1-5c746a0a80e9.png)|
|:--:|
|Counting categorical features extracted from html inside a .json file *<sup><sup>so meta, bro</sup></sup>*|
|![UFOYearsFormatted](https://user-images.githubusercontent.com/43886791/112697220-20e25400-8e55-11eb-80b1-bd1346f3c6da.png)|
|The full dataset had observations reaching back as far as the 1700s, making this plot pretty cramped|
|![UFOTop10StatesFull](https://user-images.githubusercontent.com/43886791/112699538-0f4f7b00-8e5a-11eb-98c7-c64fa2b3ddf1.png)|


Now that we had cleaned up, human readable data, it was time for machines to read instead! We elected to process the data using sklearn's CountVectorizer and feeding the resultant term frequency-inverse document frequency matrics into both Kmeans clustering and Non-Negative Matrix Featurization algorithms.

|![UFOMostCommon](https://user-images.githubusercontent.com/43886791/112696577-1b383e80-8e54-11eb-84ce-3fb8864f2082.png)|
|--|
|The
|![UFOLeastCommon](https://user-images.githubusercontent.com/43886791/112696578-1bd0d500-8e54-11eb-8b0f-5f96427779e8.png)|

|![BFMostCommon](https://user-images.githubusercontent.com/43886791/112696778-766a3100-8e54-11eb-9d54-723bf5c7ac31.png)|
|--|
|![BFClusterKMeans](https://user-images.githubusercontent.com/43886791/112696892-aadded00-8e54-11eb-87a1-0e206127b7a7.png)|

|![BigfootSightingsBySeason](https://user-images.githubusercontent.com/43886791/112696584-1e332f00-8e54-11eb-9908-7c72c227ab2f.png)|
