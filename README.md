# Classifying Age Range From Face

The goal of this project is to be able to classify age ranges by using a convolutional neural network that is trained on face images.

## Data
The data used was from the IMDB-Wiki dataset which was created by Rasmus Rothe, Radu Timofte, and Luc Van Gool at the Computer Vision Lab at ETH Zurich. The original data set contains 524,230 images that were scraped from IMDB and Wikipedia websites. These images can be downloaded from https://data.vision.ee.ethz.ch/cvl/rrothe/imdb-wiki/.

For this project, 85213 images were used to reduce the computational load of the project since there was also a time constraint. The images have metadata that describe when the image was taken, who the actor is in the photo, the actor's DOB, a full path, face score, and a second face score. 

### Exporatory Data Analysis 

The biggest question upon seeing the data is understanding the DOB which is in MATLAB datetime format. This needed to be converted back to a normal date time format. This process can be seen in the notebook titled "Data Cleaning + EDA" and understanding what face score and second face score mean. When looking at the face score data, there were about 78,000 images that contained a face score of -inf. The other faces score were in a range between a little less than 1 and 8. Images with a face score of -inf look like the image shown below. As you can see, it is a very strange picture and very hard to see any face in it. 

[some pic]

The following shows pictures with the face scores increasing from the top row to the bottom row. The top row has face scores between 0 and 1, the second row has scores between 1 and 2, and so on. 
