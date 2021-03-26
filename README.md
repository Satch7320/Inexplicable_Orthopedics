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

|![BigfootSightingsBySeason](https://user-images.githubusercontent.com/43886791/112696584-1e332f00-8e54-11eb-9908-7c72c227ab2f.png)|
|--|
|![UFOShapeFormatted](https://user-images.githubusercontent.com/43886791/112697159-090ad000-8e55-11eb-8cf1-5c746a0a80e9.png)|
|Counting categorical features extracted from html inside a .json file *<sup><sup>so meta, bro</sup></sup>*|
|![UFOYearsFormatted](https://user-images.githubusercontent.com/43886791/112697220-20e25400-8e55-11eb-80b1-bd1346f3c6da.png)|
|The full dataset had observations reaching back as far as the 1700s, making this plot pretty cramped|
|![UFOTop10StatesFull](https://user-images.githubusercontent.com/43886791/112699538-0f4f7b00-8e5a-11eb-98c7-c64fa2b3ddf1.png)|


Now that we had cleaned up, human readable data, it was time for machines to read instead! We elected to process the data using sklearn's CountVectorizer and feeding the resultant term frequency-inverse document frequency matrices into both Kmeans clustering and Non-Negative Matrix Featurization algorithms.

|![UFOMostCommon](https://user-images.githubusercontent.com/43886791/112696577-1b383e80-8e54-11eb-84ce-3fb8864f2082.png)|
|--|
|![UFOLeastCommon](https://user-images.githubusercontent.com/43886791/112696578-1bd0d500-8e54-11eb-8b0f-5f96427779e8.png)|

|![BFMostCommon](https://user-images.githubusercontent.com/43886791/112696778-766a3100-8e54-11eb-9d54-723bf5c7ac31.png)|
|--|
|The words selected by the NMF algorithm (above) differ from the KMeans algorithm below. It's difficult to say how much comes down to chance, given random initialization, but the models haven't seen all the data yet.|
|![BFClusterKMeans](https://user-images.githubusercontent.com/43886791/112696892-aadded00-8e54-11eb-87a1-0e206127b7a7.png)|

While we can see there are some curious trends here: while there are some arguable trends, why do so many of the terms seem to be grouped alphabetically? Perhaps the results are different once we featurize the entire dataset instead.

|![BFTop10WordsKMeansFull](https://user-images.githubusercontent.com/43886791/112700065-4eca9700-8e5b-11eb-9549-be8d9dd5eb6a.png)|
|--|
|![BFTop10WordsNMFFull](https://user-images.githubusercontent.com/43886791/112700068-4eca9700-8e5b-11eb-960b-e02f73d1cc79.png)|

All told, there is definite room for improvement, but it's a little tougher to diagnose where our results are most influenced. In the future, hopefully we could flesh out the NMF and KMeans algorithms we used with better tuning and come away with more informative data.

### Bonus Stuff To Look At
<img width="993" alt="HeatMapUFONear" src="https://user-images.githubusercontent.com/43886791/112700049-45d9c580-8e5b-11eb-8352-2d7275fa9e27.png">
<img width="980" alt="HeatMapUFOMid" src="https://user-images.githubusercontent.com/43886791/112700057-4a05e300-8e5b-11eb-84b5-54eea1bd9a29.png">
<img width="979" alt="HeatMapUFOFar" src="https://user-images.githubusercontent.com/43886791/112700060-4c683d00-8e5b-11eb-8293-8b378cc95c28.png">

