# Collaborative Filtering (CF)

<p align="middle">
<img src=https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/CF/framework/CF_framework.png>
</p>
<p align="middle">
    <em>CF Model Framework.</em>
</p>

# Data Preparation & Modelling

The collaborative filtering takes only one data which which is user-video activity data. Due to huge amount of data, the sampling process was used to obtained 5000 interactions. Next, the data later was transformed into suitable form which consist only student ID, course ID and Watching count. After that, the course ID was encoded by using label encoder. Subsequently, the encoded data was transformed into user-course interaction metrics. The K-nearest neighbour with cosine similarity metric and bruete algorithm was used. The model was trained in order to compute the cosine similarity of the course-user interaction metrics. In order to test the collaborative filtering, the user entity data was used and processed in similar manner as in data preparation for Multi-GAN model. The X component of test data was inputted to the model to be tested and the K-nearest neighbor will predict top five recommendation course. The code of whole process can be found in the file of ["CF_Educational_Recommendation_System"](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/CF/code/CF_Educational_Recommendation_System.ipynb) in the `code` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/CF/code)
