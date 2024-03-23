# Personalized Adaptive Learning using Generative Artificial Intelligence
![](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/assets/69446089/b2c39836-cc9a-4656-9ae7-34516aae130d)


# Background of the Study
Education has traditionally been approached using a “one size fits all” system. This traditional system has been heavily criticized in recent years for being unable to address the demands of each student. However, due to a lack of solutions, the “one size fits all” education system is still being used nowadays even with the advancement of technology. The global education systems are moving in the direction of a more individualized, student-centered strategy where the traditional "one size fits all" approach has been moved to the Smart Learning Environment (SLE). SLE requires modern technology such as Artificial Intelligence (AI), and multi-modal big data. This kind of technology must be able to have several features including tracking the learning process, identifying learning scenarios, being aware of one’s surroundings, engaging with the learning community, and simple, active, and efficient learning. In this context, SLE can be achieved through personalized or adaptive learning to improve the current educational system.

The advancement of technology has enabled learning towards a more effective learning environment where personalized learning is increasingly adaptive and adaptive learning increasingly personalized. Personalized adaptive learning is a combination of personalized learning and adaptive learning. Personalized adaptive learning can be achieved mainly by using two methods which are educational data mining and learning analytics. There are many educational data mining approaches to approach personalized adaptive learning. One of the promising technologies to achieve personalized adaptive learning in educational data mining is through a personalized recommendation system. The recommendation system in the educational field refers to a system designed to provide intelligent recommendations of learning items namely study programs, learning processes, and learning material to learners. With this system, the "personalization" and "adaptability" of learning can be achieved.

# Problem Statement

The advancement of technology has evolved the education system in a better way. Given the continuous successes and improvements of the education system, it is still far from being an optimal system. Even with the advancement of technology, the traditional approach of a "one size fits all" system is still being used in many educational institutes. The educational recommendation system that implements AI and data science methodology has been believed as one of the ways to achieve personalized adaptive learning. However, most of the conventional artificial intelligence models used in educational recommendation systems do not achieve high enough performance to meet the personal needs of the learners. Current educational recommendation systems have several notable limitations namely cold-start problems and sparsity problems associated with the collaborative filtering approach limited understanding of learning item features associated with the content-based approach and complexity of implementation which is associated with the knowledge-based approach and hybrid-based approach. With this additional limitation, the current recommendation system often did not achieve optimal performance.

# Research Questions
Due to limited studies on the implementation of the generative model in educational recommendation systems, this research aims to implement the generative model in the educational recommendation model. The research questions of the present research are formulated as follows:

1. What is the current approach to developing an educational recommendation system by implementing generative models?
2. How to implement the generative models in the educational recommendation system?
3. What is the performance of the generative models in the educational recommendation system?

# Research Objectives
Based on the formulated research questions, the study aims to:

1. To identify the current approach of the generative models in the educational recommendation system.
2. To develop an educational recommendation system by implementing generative models.
3. To evaluate the performance of the generative models in the educational recommendation system.

# Methodology
## Research Design

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/research_design/research_design.png"  width="800" />
</p>
<p align="middle">
    <em>Research Design of the Study.</em>
</p>

The study begins with a literature review to fully achieve the first objective of identifying the current approach of the generative models in learning path recommendation systems by reviewing related research papers on educational recommendation systems and generative AI. Based on the literature review, the chosen generative model is GAN due to the model offers high performance in the recommendation system. GAN is a deep learning model which can be customized to obtain the objective. Therefore, this study used four different variants of GAN to compare which one is the best model. There are four variants of the GAN model which are conventional GAN (denoted as GAN only), Multiple Generative Adversarial Networks (Multi-GAN), Multi-Discriminators Generative Adversarial Networks (MDGAN), and Multiple Multi-Discriminators Generative Adversarial Networks (Multi-MDGAN). Objective two will be achieved when the modeling part is completed which requires to model of four GAN variants. To obtain objective three, the generative model will be evaluated by using four performance metrics namely Mean Average Precision (MAP), Hit Ratio (HR), Mean Reciprocal Rank (MRR), and Normalized Discounted Cumulative Gain (NDCG). Finally, the model will be compared with conventional recommendation systems which are Collaborative Filtering (CF) and Content-Based (CB) recommendation systems. 

## Data Gathering

The chosen dataset of this study is the MOOCCube dataset which later requires some pre-processing such as entities and features selection where the important entities and features will be selected while unnecessary entities and features will be ignored; data cleaning, the mandatory data pre-processing techniques; data sampling, to make the computational cost less expensive; data transformation, transform the data into usable form; data integration where several features and entities will be combined forming desired input data; data encoding, to transform categorical data into numerical value and data splitting for model training and testing. The dataset and more explanation of the dataset can be found in the [MOOCCube](http://moocdata.cn/data/MOOCCube).

## Preprocessing & Modelling

The MOOCCube dataset comes with sub-data which later different models used different data depending on the architecture of the models. Due to the different data used and different architectures of the models, the data preparation process is also different for each model. However, all the data will be sure to undergo a data cleaning process and data understanding process to improve the decision making ability.

### GAN

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/GAN/framework/GAN_framework.png"  width="800" />
</p>
<p align="middle">
    <em>GAN Framework.</em>
</p>

GAN is a type of neural network used for generative modeling. It consists of two networks: a generator and a discriminator. The generator creates new data samples, while the discriminator tries to distinguish between real and generated samples. They are trained together in an adversarial manner, where the generator tries to fool the discriminator and the discriminator tries to become better at distinguishing real from fake. This competition leads to the generator learning to create increasingly realistic samples, making GANs useful for the main task in this project which is course recommendation. A detailed explanation of the GAN framework as well as the source code can be found in the `model\GAN` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/tree/main/model/GAN).

### Multi-GAN

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/Multi-GAN/framework/Multi-GAN_framework.png"  width="800" />
</p>
<p align="middle">
    <em>Multi-GAN Framework.</em>
</p>

Similar to GAN, Multi-GAN uses the same principle as GAN. However, Multi-GAN uses multiple GAN models to predict the top k course. The number of GAN models used is similar to the number of recommendations (k). In this project, all the recommendation is based on five recommendations which means five models of GAN were used to recommend five courses. Multi-GANs are a powerful extension of the GAN framework, allowing for a more nuanced and diverse generation of data by leveraging the strengths of multiple generative models working together. A detailed explanation of the Multi-GAN framework as well as the source code can be found in the `model\Multi-GAN` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/tree/main/model/Multi-GAN).

### MDGAN

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/MDGAN/framework/MDGAN_framework.png"  width="800" />
</p>
<p align="middle">
    <em>MDGAN Framework.</em>
</p>

MDGAN is a variation of the traditional GAN architecture that employs multiple discriminators. The main idea behind MDGAN is to improve the stability and quality of generated samples by using multiple discriminators to provide feedback to the generator. In MDGAN, there are multiple discriminators, each focusing on a different aspect or feature of the generated samples. In this case, three discriminators were used. Discriminator one will focus on the course sequence, discriminator two will focus on the school sequence, and discriminator three will focus on the teacher sequence. Using multiple discriminators can help the generator learn more effectively by receiving feedback from different perspectives. MDGANs are often more stable during training compared to traditional GANs, as the generator is trained to fool multiple discriminators simultaneously. A detailed explanation of the MDGAN framework as well as the source code can be found in the `model\MDGAN` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/tree/main/model/MDGAN).

### Multi-MDGAN

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/Multi-MDGAN/framework/Multi-MDGAN_framework.png"  width="800" />
</p>
<p align="middle">
    <em>Multi-MDGAN Framework.</em>
</p>

Similar to MDGAN, Multi-MDGAN uses the same principle as MDGAN. However, Multi-MDGAN uses multiple MDGAN models to predict the top k course. The number of MDGAN models used is similar to the number of recommendations (k). In this project, all the recommendation is based on five recommendations which means five models of MDGAN were used to recommend five courses. Multi-MDGANs extend the idea of using multiple discriminators in a GAN setup to multiple MDGANs, allowing for a more complex and nuanced generation of data by leveraging the strengths of multiple generative models working together. A detailed explanation of the Multi-MDGAN framework as well as the source code can be found in the `model\Multi-MDGAN` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/tree/main/model/Multi-MDGAN).

### CF

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/CF/framework/CF_framework.png"  width="800" />
</p>
<p align="middle">
    <em>CF Framework.</em>
</p>

CF is a technique used in recommendation systems to predict a user's preferences for items based on the preferences of other users. The basic idea behind collaborative filtering is that if two users have similar preferences for a set of items, they are likely to have similar preferences for other items as well. A detailed explanation of the CF framework as well as the source code can be found in the `model\CF` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/tree/main/model/CF).

### CB

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/CB/framework/CB_framework.png"  width="800" />
</p>
<p align="middle">
    <em>CB Framework.</em>
</p>

CB recommendation is a technique used in recommendation systems to recommend items to users based on the features or characteristics of the items and the preferences of the users. Unlike collaborative filtering, which relies on the preferences of other users, content-based recommendation focuses on the attributes of the items themselves. A detailed explanation of the CB framework as well as the source code can be found in the `model\CB` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/tree/main/model/CB).

# Evaluation

The evaluation is a process to determine how well the model predicts the final course sequence compared to the actual final course sequence from the data. However, the evaluation can be biased when the data quality is low. For example, people may take different subjects which are not related to each other causing the course sequence to become very random. Hence, reducing the model's ability to predict the final course sequence. There are four evaluation metrics used in this study which are Mean Average Precision (MAP), Hit Ratio (HR), Mean Reciprocal Rank (MRR), and Normalized Discounted Cumulative Gain (NDCG). Since the output of the recommendation model is in the form of the top five recommendations, therefore, all the mentioned metrics will become MAP@5, HR@5, MRR@5, and NDGC@5. Using these metrics provides valuable insight into system functionality and its impact on learners. By examining these metrics, it will give a better understanding of the system’s ability to meet individual needs and improve each user’s learning experience.

### Mean Average Precision (MAP)

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/evaluation/map.png"  width="800" />
</p>
<p align="middle">
    <em>MAP@5 Across Models.</em>
</p>

MAP is a metric that evaluates the quality of the recommendations. It measures both the relevance of the suggested courses and how well the system ranks these courses, particularly placing the most relevant courses higher on the list. It is particularly useful when the order of recommendations is important. From the results of MAP@5, the GAN model achieves the highest MAP of 0.016704 while the Multi-GAN model achieves the lowest MAP of 0.000586. Among the proposed models, the GAN model has the highest value of MAP which shows that GAN has the ability to precisely give relevant recommendations compared to the Multi-GAN model, MDGAN model, and Multi-MDGAN model. The GAN model has achieved an extremely significant improvement of 238% over the CF model and 100% over the CB model. The MAP@5 of the Multi-GAN model and Multi-MDGAN model is still far from the baseline model of CF and CB indicating that the Multi-GAN and Multi-MDGAN incapability to precisely give relevant recommendations compared to other models. The MDGAN model obtained MAP@5 of 0.005168, it outperforms the Multi-GAN model, Multi-MDGAN model, and CF model. It outperforms one of the baseline model CF. This shows that the multiple discriminator architecture has some degree of potential to be used as a recommendation engine. However, the MAP@5 of the MDGAN model is still below the MAP@5 of the CB model. From all the GAN variants, the conventional GAN manages to outperform both baseline models of CF and CB.

### Hit Ratio (HR) 

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/evaluation/hr.png"  width="800" />
</p>
<p align="middle">
    <em>HR@5 Across Models.</em>
</p>

HR is used to evaluate the accuracy of the recommendations. It measures correct course prediction based on the actual data. The "hit" is defined as the actual course being in the top five recommended courses while the ranking of the recommendations is ignored. It is a simple metric that indicates the percentage of hits in the recommendation list. The GAN model outperforms the other model with 0.174568 of HR@5 value while the Multi-MDGAN has the worst HR@5 value of 0.005020. The GAN model outperforms the baseline models by achieving an extremely significant improvement of 229% over the CF model and 175% over the CB model. This proves the GAN has a great degree of ability to correctly give correct recommendations compared to the other models. The MDGAN model also has shown some degree of recommendation performance where it outperforms the baseline models by achieving a relatively high improvement of 55.78% over the CF model and 29.82% over the CB model. However, the HR@5 value of the MDGAN model is still far from the GAN model.

### Mean Reciprocal Rank (MRR)

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/evaluation/mrr.png"  width="800" />
</p>
<p align="middle">
    <em>MRR@5 Across Models.</em>
</p>

MRR is a metric used to evaluate the effectiveness of a recommendation system, particularly in terms of ranking quality. It focuses on the position of the first relevant course in the ranked list of recommendations provided to the user. It is useful when the position of the first correct recommendation is more important than the overall order or the presence of other relevant courses. Similar to MAP@5 and HR@5 metrics, the GAN achieves the highest MRR@5 value compared to other models with the MRR@5 value of 0.083519 while Multi-GAN has the worst MRR value of 0.002928. The GAN model outperforms the baseline model with an extremely significant improvement of 259% over the CF model and 100% over the CB model which proves the GAN has a high degree of giving the first relevant course in the ranked list of recommendations. For MDGAN, MDGAN outperforms one of the baseline models which is CF with an 11.2% improvement. However, the MRR@5 of the MDGAN model is still below than CB model.

### Normalized Discounted Cumulative Gain (NDCG)

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/evaluation/ndcg.png"  width="800" />
</p>
<p align="middle">
    <em>NDCG@5 Across Models.</em>
</p>

NDCG is used to evaluate the ranking quality of the recommendations. It takes into account not only the relevance of each recommended item but also the order in which they are presented, with more weight given to items at the top of the list. It is a more comprehensive metric that considers both the relevance and the rank of each item. For NDCG@5, GAN again outperforms all the models with the highest value of NDCG@5 which is 0.035822. while Multi-GAN shows the lowest value of NDCG@5 which is 0.001171. GAN outperforms the baseline model by 233% of improvement over the CF model and 125% over the CB model. Meanwhile, MDGAN still outperforms one of the baseline models which is the CF model. The NDCG@5 value of MDGAN is still below the CB model.

### Overall

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/evaluation/overall.png"  width="800" />
</p>
<p align="middle">
    <em>All Performance Metrics Across Models.</em>
</p>

Overall, the GAN model outperforms all models in all performance metrics. It shows the highest value of all performance metrics. This shows the GAN model has a great degree of ability to provide better recommendations compared to the old technique of CF and CB. On the other hand, the Multi-GAN has shown the worst performance across all metrics, the worst performance is then followed by Multi-MDGAN. This indicates that the "Multi" framework of GAN is not a suitable model for this task. The MDGAN model has shown some degree of ability in the recommendations task which this model outperforms the CF model in all metrics. However, in comparison with CB, the MDGAN model manages to outperform the CB model only in the HR@5 metric. So it can be seen that the MDGAN model has a great degree in recommending accurate courses compared to baseline models as shown by HR@5 metrics. But the overall performance of MDGAN is still below the CB model and it is still very far from the winner of this task, the GAN model.

# Data Product

The data product was created by using a third-party tool, Anvil to build a website-based recommendation system. The recommendation engine includes all the models used in this study including generative models and baseline models. In this case, there are six different options for recommendation engines which are Generative Adversarial Networks, Multiple Generative Adversarial Networks, Multi-Discriminators Generative Adversarial Networks, Multiple Multi-Discriminators Generative Adversarial Networks, Collaborative Filtering, and Content-Based Filtering. The data product can be found in the ["Educational Recommendation System Application"](https://quarterly-naive-moth-course-recommender.anvil.app). Just in case the application gives an error (high probably due to the inactivity of notebooks), the overall looks and functionals of the course recommendation can be seen in the demo video below:

https://github.com/dimashidayat99/Personalized_Learning_With_GAI/assets/69446089/867bc11a-2809-4f2c-a50b-ff06aea65c9a

# Conclusion

## Revisiting the Objectives

The first objective of this study is to identify the current approach of the generative models in the educational recommendation system. The most common generative models used in the recommendation are the Boltzmann Machine, Autoregressive Model, Variational Autoencoder, Generative Adversarial Network, and Generative Language Model. However, among all the generative models, the generative adversarial network has shown powerful ability and high suitability as a recommendation engine, especially in the learning path and course sequence recommendation.

The second objective of this study is to develop an educational recommendation system by implementing a generative model. The GAN model is chosen because it offers high suitability and high performance compared to other models. The data product of the educational recommendation system based on the Generative Adversarial Network has been developed by using four variants of the GAN which are GAN, Multi-GAN, MDGAN, and Multi-MDGAN together with other baseline models which are CF and CB. 

The final objective of this research is to evaluate the performance of the generative models in the educational recommendation system. The generative model was evaluated based on the performance metrics of MAP, HR, MRR, and NDCG. The performance of generative models was compared with each other and the baseline model of CF and CB. The GAN model outperforms all models in all performance metrics. It shows the highest value of all performance metrics. Therefore, the GAN model is the best model to be used in the recommendations task compared to the other models that used in this study.

## Contributions
The successful implementation of generative AI in educational recommendation systems makes a significant contribution to this field. The main contribution of this study is to develop an educational recommendation system based on generative models. To the best of my knowledge, this study first introduces GAN to the recommendation task in the education field. Next, the study identified the generative model has shown to have a high degree of performance as a recommendation engine. The results showed that the use of generative models especially the GAN model increased up to 200% in all metrics which is an extremely significant improvement over baseline models. This contribution advances the field of educational recommendation systems providing a new approach to enhancing the performance of the recommendation system, with potential applications in educational platforms or educational institutions. Overall, this study has provided better insights into the generative models to provide adaptability and personalization of the learning environment.

## Limitations
This study has several limitations. Mainly, the study faces issues with limited computational resources where the RAM of the system in the Google Collaboratory free tier is limited. The insufficient computational resources will lead to another limitation of this study which is limited model optimization. The important process of model optimization through hyperparameter tuning which may give relatively high improvement to the results can not be done due to the limited computational resources. Next, the insufficient computational resources limit the model architecture to have a more complex model which may give better performance for generative models. This will cause the study to use the lowest level of the model’s architecture where the advanced architecture is not being explored in this study. The low computational resource also forces the model to run in a small number of iterations which may result in difficulty in finding the global or local minimum of the loss function of generative models causing the instability of the model during model training. Usually, the generative model requires training over 500 epochs. Last but not least, the study has faced a limited understanding of the dataset due to the dataset being written not in the English language. The dataset is written in the Chinese language which makes the difficult to understand the data. Since the dataset is huge, translating the dataset or desired data from the dataset will take a lot of time. The language barrier caused the data preparation process and deployment to become challenging and less effective.

## Future Works
The objective of the research has been accomplished with the main findings of generative models that have shown improvement in recommendation systems compared to conventional models. However, there are an infinite number of possibilities of methodology which can be used to achieve the best results. Due to the limitations of this research, there are several ideas have been left for future work. Firstly, the generative models are suggested to have more advanced architecture such as adding an attention layer, implementing transformer architecture, and adding recurrent neural networks in both components (generator and discriminator). With advanced architecture, theoretically, it will improve the results significantly based on past research. Due to the limitations mentioned, this study ignores the model optimization. Therefore, it is highly suggested to conduct the model's optimization to find the optimum hyperparameter to obtain optimum performance. Last but not least, future studies should implement different generative models to become recommendation engines, this will give a better view of the overall family of generative models on its performance in the educational field. This includes implementing different variants of each generative model since generative models have a lot of variants while the effectiveness of each variant is surely the least being explored especially in the education field.

