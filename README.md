# MODIS Cloud Detection with ML

This project explores the usage of machine learning methods for identifying instances of clouds (pixel level) on Satellite images from the MODIS satellite cluster.

Presentation Link (sign in with @illinois.edu): https://docs.google.com/presentation/d/1jAE32Gbe-n0vYUJEh69vcMN_dsS3Q4r6IP_VQoU7ctg/edit?usp=sharing
The presentation includes the rationale for choosing a Machine Learning approach over a Deep Learning approach for this specific problem.

Our PCA implementation is included in PCA.ipynb

# Development


The Machine Learning model was trained on all of the images within the /home/hackathon/output_64_Javier_labelled/ directory provided on HAL that contained Ground Truths that 
were classified as "Good", i.e. "1". In total, the model was trained on 115 images.

The dataset for this model was created by converting all 115 images and their corresponding 43 bands into a Pandas dataframe containing 115 * 64 * 64 (64 is the 
width and height of the images) rows and 43 columns, for a total of **20,254,720** datapoints. A 44th column was added, with the corresponding Ground Truth values
by converting values from the Image_Classification (Groud Truth image) to either 0 (if the value was 0) or 1 (if the value was 1,2, or 3).


A Logistic Regression model using all 43 bands was then trainied to classify each pixel in each image as either 0 or 1 based on the Ground Truth (44th) column. 

For generating visuals, we plotted the Image_Classification (Groud Truth image) along side our predicted image by reconstructing consecutive blocks of 4096 (64 * 64)
rows back to a numpy array of 64 * 64 and plotting that array.


# Accuracy


The accuracy of our model on a test dataset consisting of 20% of all of the rows from our pandas dataframe is **97.5%**.

The following are the accuracy scores of our model on the new images (not from the  115 images that our model is trained on) that Javier has 
provided after the conclusion of the hackathon.

image_0: 100%

image_12: 100%

image_17: 100%

image_24: 79.46%

image_59: 98.73%

image_119: 99.05%

image_130: 98.36%

image_145 99.71%

image_157: 99.39%

image_162: 98.68%

image_170: 98.22%

image_178: 99.41%


# Team

Pranshu Chaturvedi

Rohan Prasad

Gaurav Krishnan

Shashank Mahesh
