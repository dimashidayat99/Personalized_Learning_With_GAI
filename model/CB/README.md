# Content-Based (CB)

<p align="middle">
<img src=https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/CB/framework/CB_framework.png>
</p>
<p align="middle">
    <em>CB Model Framework.</em>
</p>

# Modelling & Preprocessing

The content-based filtering used three data as train data. The course entity data, teacher course relation data and school course relation data was combined together to form course data with school and teacher features. The features of course information, teacher and school was combined together to form combined features. The only combined feature was selected to undergo string replacement process where the features was processed to make sure the string in combined features is cleaned. The cleaned string in combined feature as processed further for feauture extraction by using Term Frequency-Inverse Document Frequency (TD-IDF) to weight to each word in the feature based on its term frequency and the reciprocal document frequency. Next, the processed data was used to calculated the cosine similarity. This similarity was used to find top five recommended courses. The X component of test data was obtained from the user entity data by similar process as in data preparation in Multi-GAN model. The X component of test data was used for model testing to give top five recommendations. The code of whole process can be found in the file of ["CB_Educational_Recommendation_System"](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/CB/code/CB_Educational_Recommendation_System.ipynb) in the `code` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/CB/code).

