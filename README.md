# Classifying Age Range From Face

The goal of this project is to be able to classify age ranges by using a convolutional neural network that is trained on face images.

## Data
The data used was from the IMDB-Wiki dataset which was created by Rasmus Rothe, Radu Timofte, and Luc Van Gool at the Computer Vision Lab at ETH Zurich. The original data set contains 524,230 images that were scraped from IMDB and Wikipedia websites. These images can be downloaded from https://data.vision.ee.ethz.ch/cvl/rrothe/imdb-wiki/.

For this project, 85,213 images were used to reduce the computational load of the project due to time constraints. The images have metadata which describe when the image was taken as well as information about the actor in the photo such as the actor's DOB, a full path, face score, and a second face score. The image below shows some examples of the meta data. 

<img src="Images/MetaData.png" width = "600"/>


### Exporatory Data Analysis 

The biggest question upon first seeing the data is understanding the DOB which is in MATLAB datetime format. This needed to be converted back to a normal date time format. This process can be seen in the notebook titled "Data Cleaning + EDA". The following steps were done in order to better understand the meta data, specifically face score and second face score. When looking at the face score data, there were about 78,000 images that contained a face score of -inf. Some examples of images with -inf scores can be seen below:

<img src = "Images/picneginf_1.png" width = "200" /> <img src = "Images/picneginf_2.png" width = "300"/>

It is evident from these images, that images with face scores of -inf should be removed since no face image can even be discerned from these pictures. The other face score were in a range between a little less than 1 and 8. To get a better understanding of how the images change as the face scores change, images with different face scores were looked at. So in the table of images below, the first row contains images with face scores between 0 and 1, the second row contains scores between 1 and 2, so on and so forth. 

<img src= "Images/facescores_table.png" width = "600"/>

From this table, it can be seen that as the face score improves, the faces become more centered, the face is more distinct from its background and the people in the pictures are looking straight forward. 

After this, second face score was examined using a similar approach. The picture below summarizes the relationship that was observed. 

<img src = "Images/secondfacescores.JPG" width = "600"/>

It was seen that once second facescores crosses a certain threshold, there is a second face in the picture. This score happenned to be around 3.1. So images that had a second face score greater than 3.1 were removed. So after removing these pictures, as well as pictures that had ages that didn't make sense, there were about 381,000 pictures. The following graph shows the distribution of the labeled ages of the pictures. 

<img src = "Images/ages_distribution.png" width = "600"/>

After removing pictures that were labeled under the age of 10 and older than 70, the pictures were put into bins of age ranges. In order to balance pictures, many pictures had to be removed as well. After this, there were about 86,000 pictures left. 

#### Base CNN Model 



