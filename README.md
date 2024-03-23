# Personalized Adaptive Learning using Generative Artificial Intelligence
![](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/assets/69446089/b2c39836-cc9a-4656-9ae7-34516aae130d)


# Background of the Study
Education has traditionally been approached using a “one size fits all” system. This traditional system has been heavily criticised in recent years for being unable to address the demands of each individual student. However, due to lack of solution, the “one size fits all” education system is still being used nowadays even with advancement of technology. The global education systems are moving in the direction of a more individualized, student-centered strategy where traditional "one size fits all" approach has been moved to the Smart Learning Environment (SLE). SLE required modern technology such as Artificial Intelligence (AI), and multi-modal big data. These kind of technologies must be able to have several features including tracking the learning process, identifying learning scenarios, being aware of one’s surroundings, engaging with the learning community, and simple, active, and efficient learning. In this context, SLE can be achieved through personalized or adaptive learning to improving the current educational system.

The advancement technology has enabled learning towards more effective learning environment where personalized learning increasingly adaptive and adaptive learning increasingly personalized. The personalized adaptive learning is a combination of personalized learning and adaptive learning. The personalized adaptive learning can be achieved mainly by using two methods which are educational data mining and learning analytic. There are many educational data mining approach for approaching the personalized adaptive learning. One of the promising technology to achieve personalized adaptive learning in educational data mining is through personalized recommendation system. The recommendation system in educational field refer to a system designed to provide intelligent recommendations of learning items namely study program, learning processes and learning material to learners. With this system, the "personalization" and "adaptability" of learning can be achieved.

# Problem Statement

The advancement of technology has evolved the education system to better way. Given the continuous successes and improvements of the education system, it is still far from being optimal system. Even with advancement of technology, the traditional approach of "one size fits all" system is still being used in many educational institute. The educational recommendation system which implementing AI and data science methodology has been believed as one of the way to achieve personalized adaptive learning. However, most of the conventional artificial intelligence and model used in educational recommendation system does not achieve high enough performance to provide the personal needs of the learners. Current educational recommendation systems have several notable limitations namely cold-start problems and sparsity problems associated with collaborative filtering approach limited understanding of learning item features associated with content-based approach and complexity of implementation which associated with knowledge-based approach and hybrid-based approach. With this additional limitation, the current recommendation system often did not achieve optimal performance.

# Research Questions
Due to limited study on implementation of generative model in educational recommendation system, this research aims to implement the generative model in educational recommendation model. The research questions of present research is formulated as follows:

1. What are the current approach of developing educational recommendation system by implementing generative model ?
2. How to implement the generative model in educational recommendation system ?
3. What is the performance of generative model in educational recommendation system ?

# Research Objectives
Based on the formulated research questions, the study aims to:

1. To identify the current approach of generative model in the educational recommendation system.
2. To develop educational recommendation system by implementing generative model.
3. To evaluate the performance of generative model in the educational recommendation system.

# Methodology
## Research Design

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/research_design/research_design.png"  width="800" />
</p>
<p align="middle">
    <em>Research Design of the Study.</em>
</p>

The study begins with literature review to fully achieve the objective one which to identify current approach of generative model in learning path recommendation system by reviewing related research paper of educational recommendation system and generative AI. Based on the literature review, the chosen generative model is GAN due to the model offer high performance in the recommendation system. GAN is a deep learning model which can be customized to obtained the objective. Therefore, this study used four different variant of GAN to compared which one is the best model. There are four variant of the GAN model which are conventional GAN (denoted as GAN only), Multiple Generative Adversarial Networks (Multi-GAN), Multi-Discriminators Generative Adversarial Network (MDGAN) and Multiple Multi-Discriminators Generative Adversarial Networks (Multi-MDGAN). The objective two will be achieved when modelling part is completed which require to model four GAN variants. To obtain objective three, the generative model will be evaluated by using four performance metrics namely Mean Average Precision (MAP), Hit Ratio (HR), Mean Reciprocal Rank (MRR) and Normalized Discounted Cumulative Gain (NDCG). Finally, the model will be compared with conventional recommendation system which are Collaborative Filtering (CF) and Content Based (CB) recommendation system. 

## Data Gathering

The chosen dataset of this study is MOOCCube dataset which later require some pre-processing such as entities and features selection where the important entities and features will be selected while unnecessary entities and features will be ignored; data cleaning, the mandatory data pre-processing techniques; data sampling, to make the computational cost less expensive; data transformation, transform the data into usable form; data integration where several features and entities will be combined together forming desired input data; data encoding, to transform categorical data into numerical value and data splitting for model training and testing. The dataset and more explanation of the dataset can be found in the [MOOCCube](http://moocdata.cn/data/MOOCCube).

## Preprocessing & Modelling

The MOOCCube dataset come with sub data which later different model used different data depending on the architecture of the models. Due to different data was used and different architecture of the models, the data preparation process is also different for each models. However, all the data will make sure undergo data cleaning process and data understanding process to improved the decision making ability.

### GAN

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/GAN/framework/GAN_framework.png"  width="800" />
</p>
<p align="middle">
    <em>GAN Framework.</em>
</p>

GAN is a type of neural network used for generative modeling. It consists of two networks: a generator and a discriminator. The generator creates new data samples, while the discriminator tries to distinguish between real and generated samples. They are trained together in an adversarial manner, where the generator tries to fool the discriminator and the discriminator tries to become better at distinguishing real from fake. This competition leads to the generator learning to create increasingly realistic samples, making GANs useful for the main task in this project which is course recommendation. A detail explanation of the GAN framework as well as the source code can be found in the `model\GAN` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/tree/main/model/GAN).

### Multi-GAN

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/Multi-GAN/framework/Multi-GAN_framework.png"  width="800" />
</p>
<p align="middle">
    <em>Multi-GAN Framework.</em>
</p>

Similar with GAN, Multi-GAN use same principle as GAN. However, Multi-GAN use multiple GAN model to predict the top k course. The number of GAN model used is similar with the number of recommendation (k). In this project, all the recommendation is based of five recommendation which means five model of GAN was used to recommend five courses. Multi-GANs are a powerful extension of the GAN framework, allowing for more nuanced and diverse generation of data by leveraging the strengths of multiple generative models working together. A detail explanation of the Multi-GAN framework as well as the source code can be found in the `model\Multi-GAN` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/tree/main/model/Multi-GAN).

### MDGAN

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/MDGAN/framework/MDGAN_framework.png"  width="800" />
</p>
<p align="middle">
    <em>MDGAN Framework.</em>
</p>

MDGAN is a variation of the traditional GAN architecture that employs multiple discriminators. The main idea behind MDGAN is to improve the stability and quality of generated samples by using multiple discriminators to provide feedback to the generator. In MDGAN, there are multiple discriminators, each focusing on a different aspect or feature of the generated samples. In this case, three discriminators were used. Discriminator one will focus on the course sequence, discriminator two will focus on school sequence and discriminator three will focus on teacher sequence. Using multiple discriminators can help the generator learn more effectively by receiving feedback from different perspectives. MDGANs are often more stable during training compared to traditional GANs, as the generator is trained to fool multiple discriminators simultaneously. A detail explanation of the MDGAN framework as well as the source code can be found in the `model\MDGAN` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/tree/main/model/MDGAN).

### Multi-MDGAN

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/Multi-MDGAN/framework/Multi-MDGAN_framework.png"  width="800" />
</p>
<p align="middle">
    <em>Multi-MDGAN Framework.</em>
</p>

Similar with MDGAN, Multi-MDGAN use same principle as MDGAN. However, Multi-MDGAN use multiple MDGAN model to predict the top k course. The number of MDGAN model used is similar with the number of recommendation (k). In this project, all the recommendation is based of five recommendation which means five model of MDGAN was used to recommend five courses. Multi-MDGANs extend the idea of using multiple discriminators in a GAN setup to multiple MDGANs, allowing for more complex and nuanced generation of data by leveraging the strengths of multiple generative models working together. A detail explanation of the Multi-MDGAN framework as well as the source code can be found in the `model\Multi-MDGAN` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/tree/main/model/Multi-MDGAN).

### CF

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/CF/framework/CF_framework.png"  width="800" />
</p>
<p align="middle">
    <em>CF Framework.</em>
</p>

CF is a technique used in recommendation systems to predict a user's preferences for items based on the preferences of other users. The basic idea behind collaborative filtering is that if two users have similar preferences for a set of items, they are likely to have similar preferences for other items as well. A detail explanation of the CF framework as well as the source code can be found in the `model\CF` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/tree/main/model/CF).

### CB

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/model/CB/framework/CB_framework.png"  width="800" />
</p>
<p align="middle">
    <em>CB Framework.</em>
</p>

CB recommendation is a technique used in recommendation systems to recommend items to users based on the features or characteristics of the items and the preferences of the users. Unlike collaborative filtering, which relies on the preferences of other users, content-based recommendation focuses on the attributes of the items themselves. A detail explanation of the CB framework as well as the source code can be found in the `model\CB` [directory](https://github.com/dimashidayat99/Personalized_Learning_With_GAI/tree/main/model/CB).

# Evaluation

The evaluation is a process to determine how well the model predicts the final course sequence compared to the actual final course sequence from the data. However, the evaluation can be biased when the data quality is low. For example, people may take different subjects which are not related to each other causing the course sequence to become very random. Hence, reducing the model's ability to predict the final course sequence. There are four evaluation metrics used in this study which are Mean Average Precision (MAP), Hit Ratio (HR), Mean Reciprocal Rank (MRR) and Normalized Discounted Cumulative Gain (NDCG). Since the output of the recommendation model is in the form of top five recommendation, therefore, all the mentioned metrics will become MAP@5, HR@5, MRR@5 and NDGC@5. Using these metrics, it provide valuable insight into system functionality and its impact on learners. By examining these metrics, it will give better understanding of the system’s ability to meet individual needs and improve each user’s learning experience.

### Mean Average Precision (MAP)

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/evaluation/map.png"  width="800" />
</p>
<p align="middle">
    <em>MAP@5 Across Models.</em>
</p>

MAP is a metric thatt evaluates the quality of the recommendations. It measures both the relevance of the suggested courses and how well the system ranks these courses, particularly placing the most relevant courses higher on the list. It is particularly useful when the order of recommendations is important. From the results of MAP@5, the GAN model achieve highest MAP of 0.016704 whlie Multi-GAN model achieve lowest MAP of 0.000586. Among the proposed model, the GAN model has highest value of MAP which show that GAN has the ability to precisely give relevant recommendation compared to Multi-GAN model, MDGAN model and Multi-MDGAN model. The GAN model have achieve extreme significant improvement of 238% compared to CF model and 100% compared to CB model. The MAP@5 of Multi-GAN model and Multi-MDGAN model is still far from the baseline model of CF and CB indicates that the Multi-GAN and Multi-MDGAN incapatibility to precisely give revelant recommendation compared to other models. The MDGAN model obtained MAP@5 of 0.005168, it outperform Multi-GAN model, Multi-MDGAN model and CF model. It outperform one of the baseline model CF. This shows that the multiple discriminators architecture have some degree of potential to be used as recommendation engine. However, the MAP@5 of MDGAN model still below than the MAP@5 of CB model. From all the GAN variant, the conventional GAN manage to outperform both baseline model of CF and CB.

### Hit Ratio (HR) 

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/evaluation/hr.png"  width="800" />
</p>
<p align="middle">
    <em>HR@5 Across Models.</em>
</p>

HR is used to evaluate the accuracy of the recommendations. Its measure correct course prediction based on the actual data. The "hit" is defined as the actual course is in the top five recommended courses while the ranking of the recommendations are ignored. It is a simple metric that indicates the percentage of hits in the recommendation list. The GAN model outperform the other model with 0.174568 of HR@5 value while the Multi-MDGAN has the worst HR@5 value of 0.005020. The GAN model outperform the baseline models by achieve extreme significant improvement of 229% compared to CF model and 175% compared to CB model. This prove the GAN has great degree of ability to correctly give correct recommendations compared to the other models. The MDGAN model also has shown some degree of recomendations performance where it outperform the baseline models by achieving relatively high improvement of 55.78% compared to CF model and 29.82% compared to CB model. However, the HR@5 value of MDGAN model is still far from the GAN model.

### Mean Reciprocal Rank (MRR)

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/evaluation/mrr.png"  width="800" />
</p>
<p align="middle">
    <em>MRR@5 Across Models.</em>
</p>

MRR is a metric used to evaluate the effectiveness of a recommendation system, particularly in terms of ranking quality. It focuses on the position of the first relevant course in the ranked list of recommendations provided to the user. It is useful when the position of the first correct recommendation is more important than the overall order or the presence of other relevant courses. Similar with MAP@5 and HR@5 metrics, the GAN achieve highest MRR@5 value compared to other models with the MRR@5 value of 0.083519 while Multi-GAN has the worst MRR value of 0.002928. The GAN model outperform the baseline model with extreme significant improvement of 259% compared to CF model and 100% compared to CB model which prove the GAN has high degree of giving first revelant course in the ranked list of recommendations. While for MDGAN, it outperform one of the baseline model which is CF with 11.2%  of improvement. However, the MRR@5 of MDGAN model is still below than CB model.

### Normalized Discounted Cumulative Gain (NDCG)

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/evaluation/ndcg.png"  width="800" />
</p>
<p align="middle">
    <em>NDCG@5 Across Models.</em>
</p>

NDCG is used to evaluate the ranking quality of the recommendations. It takes into account not only the relevance of each recommended item but also the order in which they are presented, with more weight given to items at the top of the list. It is a more comprehensive metric that considers both the relevance and the rank of each item. For NDCG@5, GAN again outperform all the models with the highest value of NDCG@5 which is 0.035822. while Multi-GAN shows the lowest value of NDCG@5 which is 0.001171. GAN outperform the baseline model by 233% of imporvement compared to CF model and 125% compared to CB model. Meanwhile for MDGAN, it still outperform one of the baseline model which is CF model. The NDCG@5 value of MDGAN is still below the CB model.

### Overall

<p align="middle">
<img src="https://github.com/dimashidayat99/Personalized_Learning_With_GAI/blob/main/evaluation/overall.png"  width="800" />
</p>
<p align="middle">
    <em>All Performance Metrics Across Models.</em>
</p>

Overall, the GAN model outperform all models in all performance metrics. It shows highest value of all performance metrics. This shows the GAN model has a great degree of ability to provide a better recommendations compared to the old technique of CF and CB. On the other hand, the Multi-GAN has shown the worst performance across all metrics, the worst performance is then followed by Multi-MDGAN. This indicates that the "Multi" framework of GAN is not suitable model in this task. The MDGAN model has shown some degree of ability in the recommendations task which this model outperform the CF model in all metrics. However, in comparison with CB, the MDGAN model manage to outperform the CB model only in the HR@5 metric. So it can be seen that MDGAN model have a great degree in recommending accurate course compared to baseline models as shown by HR@5 metrics. But overall performance of MDGAN is still below CB model and it still very far from the winner of this task, GAN model.

# Data Product

The data product was created by using third party tools which is Anvil to build a website based recommendation system. The recommendation engine includes all the models used in this study including generative models and baseline models. In this case, there are six different options of recommendation engine which are Generative Adversarial Networks, Multiple Generative Adversarial Networks, Multi-Discriminators Generative Adversarial Network, Multiple Multi-Discriminators Generative Adversarial Networks, Collaborative Filtering and Content-Based Filtering. The data product can be found in ["Educational Recommendation System Application"](https://quarterly-naive-moth-course-recommender.anvil.app). Just in case the application give an error (high probably due to inactivity of notebooks), the overall of looks and functionals of the course recommendation can be seen in the demo video below:

https://github.com/dimashidayat99/Personalized_Learning_With_GAI/assets/69446089/867bc11a-2809-4f2c-a50b-ff06aea65c9a

# Conclusion

## Revisiting the Objectives

The first objective of this study is to identify the current approach of generative model in the educational recommendation system. The most common generative models used in the recommendation are Boltzmann Machine, Autoregressive Model, Variational Autoencoder, Generative Adversarial Network and Generative Language Model. However, among all the generative models, the generative adversarial network has shown powerful ability and high suitability as a recommendation engine especially in the learning path and course sequence recommendation.

The second objective of this study is to develop the educational recommendation system by implementing generative model. The GAN model is chosen because it offer high suitability and high performance compared to other models. The data product of educational recommendation system based on Generative Adversarial Network has been developed by using four variant of the GAN which are GAN, Multi-GAN, MDGAN and Multi-MDGAN together with another to baseline models which are CF and CB. 

The final objective of this research is to evaluate the performance of generative model in the educational recommendation system. The generative model was evaluated based on performance metrics of MAP, HR, MRR and NDCG. The performance of generative models was compared with each other and the baseline model of CF and CB. The GAN model outperform all models in all performance metrics. It shows highest value of all performance metrics. Therefore, GAN model is the best model to be used in the recommendations task compared to the other models that used in this study.

## Contributions
The successful implementation of generative AI in educational recommendation system give significant contribution in this field. The main contribution of this study is developed educational recommendation system based on generative model. To the best of my knowledge, this study first to introduce generative adversarial network into the recommendation task in education field. Next, the study identified the generative model has shown to have high degree of performance as a recommendation engine. The results showed that the use of generative models especially GAN model increased up to 200% in all metrics which is an extremely significant improvement over baseline models. This contribution advances the field of educational recommendation system providing a new approach to enhancing the performance of the recommendation system, with potential applications in educational platform or educational institution. Overall, this study has provide better insights for the generative models to provide adaptability and personalization of the learning environment.

## Limitations
This study has several limitations. Mainly, the study face issues on limited computational resources where the RAM of the system in Google Collaboratory free tier is limited. The insufficient of computational resource will lead to another limitation of this study which is limited model’s optimization. The important process of model optimization through hyperparameter tuning which may give relative high improvement to the results can not be done due to the limited computational resources. Next, the insufficient computational resources limit the model architecture to have more complex model which may give better performance for generative models. This will cause the study to used lowest level of model’s architecture where the advanced architecture is not being explored in this study. The low computational resource also force the model to run in small number of iteration which may resulting on difficulty to find global or local minimum of the loss function of generative models causing the instability of the model during model training. Usually the generative model require to train over than 500 epoch. Last but not least, the study has face limited understanding of the dataset due to the dataset is written not in English language. The dataset is written in Chinese language which give the difficulty to understand the data. Since the dataset is huge, translating the dataset or desired data from dataset will takes a lot of times. The language barrier causing the data preparation process and deployment become challenging and less effective.

## Future Works
The objective of the research has been accomplished with the main findings of generative models has shown improvement in recommendation system compared to conventional models. However, there are infinite number of possibilities of methodology which can be used in order to achieve the best results. Due to limitations of this research, there are several ideas have been left for the future work. Firstly, the generative models is suggested to have more advanced architecture such as adding attention layer, implement transformer architecture and adding recurrent neural network in the both component (generator and discriminator). With advanced architecture, theoretically, it will improved the results significantly based on past research. Due to limitations as mentioned, this study ignore the model optimization. Therefore, it highly suggested to conduct model's optimization to find optimum hyperparameter to obtain optimum performance. Last but not least, future study should implement different generative models to become recommendation engine, this will give better view on overall family of generative model on the its performance in educational field. This includes to implement different variant of each generative models since generative model have a lot of variant while the effectiveness of each variant is surely least being explore especially in education field.

