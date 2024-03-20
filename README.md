# Background of the Study
Education has traditionally been approached using a “one size fits all” system. This traditional system has been heavily criticised in recent years for being unable to address the demands of each individual student. This system assumes all students learn in the same ways but in fact that each student learns differently in many ways due to the difference in personalities, backgrounds, physical characteristics, cognitive abilities, experiences, learning preferences, social development as well as learning needs for each student. However, due to lack of solution, the “one size fits all” education system is still being used nowadays even with advancement of technology. Global education systems are moving in the direction of a more individualized, student-centered strategy where traditional "one size fits all" approach has been moved to the Smart Learning Environment (SLE). SLE required modern technology such as Artificial Intelligence (AI), and multi-modal big data. These kind of technologies must be able to have several features including tracking the learning process, identifying learning scenarios, being aware of one’s surroundings, engaging with the learning community, and simple, active, and efficient learning. In this context, SLE can be achieved through personalized or adaptive learning to improving the current educational system.

The personalized learning has been the main goal in the educational system. With the evolution of technology, the personalized learning has become more complex. Personal learning is defined as education where the learning pace and instructional technique are tailored to the needs of each learner and where the learning activities are pertinent to the subjects being studied, motivated by the interests of the students, and frequently self initiated. On the other hand, the adaptive learning has no unified view on the concept, it has many definitions as personalized learning. In general, adaptive learning is widely accepted as learning mode that provides corresponding learning environment. With the integration of technology, the adaptive learning today is considered as an educational technology rather than method.

The advancement technology has enabled learning towards more effective learning environment where personalized learning increasingly adaptive and adaptive learning increasingly personalized. The personalized adaptive learning is a combination of personalized learning and adaptive learning. The personalized adaptive learning can be achieved mainly by using two methods which are educational data mining and learning analytic. There are many educational data mining approach for approaching the personalized adaptive learning. One of the promising technology to achieve personalized adaptive learning in educational data mining is through personalized recommendation system. The recommendation system in educational field refer to a system designed to provide intelligent recommendations of learning items namely study program, learning processes and learning material to learners. With this system, the "personalization" and "adaptability" of learning can be achieved.

# Problem Statement

he advancement of technology has evolved the education system to better way. Given the continuous successes and improvements of the education system, it is still far from being optimal system. Even with advancement of technology, the traditional approach of "one size fits all" system is still being used in many educational institute. The personalized adaptive learning namely, is one of the domain that attract so many attention in recent year to achieve optimal education system. With help of artificial intelligence (AI), the process approaching personalized adaptive learning can be shorten. Educational recommendation system which implementing AI and data science methodology has been believed as one of the way to achieve personalized adaptive learning. The educational recommendation system has shown the ability to provide personalized learning through recommending the learning items based on learner needs. However, the problems and gaps still occur in the existing educational recommendation system where most of the conventional AI used in educational recommendation system does not achieve high enough performance to provide the personal needs of the learners. Also, the current educational recommendation systems have several notable limitations namely cold-start problems and sparsity problems associated with collaborative filtering approach , limited understanding of learning item features associated with content-based approach and complexity of implementation which associated with knowledge-based approach and hybrid based approach. With this additional limitation, the recommendation system often did not achieve optimal performance. Recently, the rise of generative AI has drawn so many attention due to its performance. Implementing the generative models in the recommendation system has shown great performance and achieve significance improvement of the performance compared to conventional recommendation model. Despite the performance, there is a limited study on implementing the generative model in the education field especially in the educational recommendation system. To best of my knowledge, there is no study that use generative model to generate the learning path to achieve personalized adaptive learning.

# Research Questions
Due to limited study on implementation of generative model in educational recommendation system, this research aims to implement the generative model in educational recommendation model. The research questions of present research is formulated as follows:
1. What are the current approach of developing educational recommendation system by implementing generative model ?
2. How to implement the generative model in educational recommendation system ?
3. What is the performance of generative model in educational recommendation system ?

# Research Objectives
Based on the formulated research questions, the study aims to:
1. To identify the current approach of generative model in the educational recommendation system.
2. To develop educational recommendation system by implementing generative model.
3. To evaluate the performance of generative model in the educational recommendation system.

# Methodology
## Research Design

![]()

Overall Idea, this study will implement a quantitative experimental approach to its research design where the proposed system is only limited for computational study while empirical study is not being conducted in this study due to time constraint. The research begins with literature review to fully achieve the objective one which to identify current approach of generative model in learning path recommendation system by reviewing related research paper of educational recommendation system and generative AI. Based on the literature review, the chosen generative model is GAN due to the model offer high performance in the recommendation system. GAN is a deep learning model which can be customized to obtained the objective. Therefore, this study used four different variant of GAN to compared which one is the best model. There are four variant of the GAN model which are conventional GAN (denoted as GAN only), Multiple Generative Adversarial Networks (Multi-GAN), Multiple Discriminator Generative Adversarial Network (MDGAN) and Multiple Multiple Discriminators Generative Adversarial Networks (Multi-MDGAN). 

The objective two will be achieved when modelling part is completed which require to model four GAN variants. To obtain objective three, the generative model will be evaluated by using four performance metrics namely mean average precision, hit ratio, mean reciprocal rank and normalized discounted cumulative gain. Finally, the model will be compared with conventional recommendation system such collaborative filtering and content based recommendation system. The both baselines is chosen due to simplicity. The other approach will not being used as the baseline because of the complexity and time constraint.

## Data Gathering

The chosen dataset of this study is [MOOCCube](http://moocdata.cn/data/MOOCCube) dataset which later require some pre-processing such as entities and features selection where the important entities and features will be selected while unnecessary entities and features will be ignored; data cleaning, the mandatory data pre-processing techniques; data sampling, to make the computational cost less expensive; data transformation, transform the data into usable form; data integration where several features and entities will be combined together forming desired input data; data encoding, to transform categorical data into numerical value and data splitting for model training and testing. The dataset and more explanation of the dataset can be found in `` [directory]().

## Preprocessing & Modelling

### GAN

GAN is a type of neural network used for generative modeling. It consists of two networks: a generator and a discriminator. The generator creates new data samples, while the discriminator tries to distinguish between real and generated samples. They are trained together in an adversarial manner, where the generator tries to fool the discriminator and the discriminator tries to become better at distinguishing real from fake. This competition leads to the generator learning to create increasingly realistic samples, making GANs useful for the main task in this project . A detail explanation of the GAN framework as well as the source code can be found in the `` [directory]()
### Multi-GAN
### MDGAN
### Multi-MDGAN

# Results & Evaluation

## Evaluation - Actualness
### Mean Average Precision (MAP)
### Hit Ratio (HR) 
### Mean Reciprocal Rank (MRR)
### Normalized Discounted Cumulative Gain (NDCG)
### Overall

## Evaluation - Relevancy
### Mean Average Precision (MAP)
### Hit Ratio (HR) 
### Mean Reciprocal Rank (MRR)
### Normalized Discounted Cumulative Gain (NDCG)
### Overall

# Data Product

# Conclusion
## Contributions
## Limitations
## Future Works

