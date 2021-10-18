# MAB-vs-AB-Testing-for-Recommender-Systems


## Description

In this case study, the performance of MAB algorithms were compared against statistical tests like A/B testing in an online recommendation setting.
I used the Anime Recommendation Database 2020 from Kaggle (https://www.kaggle.com/hernan4444/anime-recommendation-database-2020) to conduct this case study.
To reduce losses incurred during testing I implemented a bootsrapped-replay buffer to simulate online testing in an offline enviroment. The details of the buffer are
mentioned in the paper- https://arxiv.org/abs/1003.5956

The "anime_eda.ipynb" notebook contains the exploratory data analysis and the cleaning required to make the dataset fit our usecase. I filtered the top 10 most reviewed anime
which were rated on a scale of 1-10. For a rating of 10, I gave a reward of 1 during simulations, indicating that if this anime was recommended, the user would like it.
For all other ratings, the recommendation would yield a reward of 0.

The task of the competing algorithms is to identify the most liked anime as quickly as possible and recommend it to maximum audience to increase gains.

The "simulator.ipynb" simulated the recommendation setting and evaluates the performance of each algorithm


### Results

1.) Estimated Expected Rewards for each algorithm

![1 yo](https://user-images.githubusercontent.com/57484266/137715224-873a3797-59d8-4035-8186-036ad570f9eb.PNG)


2.) Average Normalised Rewards per iteration

![1](https://user-images.githubusercontent.com/57484266/137715237-135c4110-b576-4b01-a560-d9616c23f6f6.PNG)


3.) Percentage Optimal Recommendations

![2](https://user-images.githubusercontent.com/57484266/137715243-4d9ab2d0-4bdf-416d-b513-1a492ae34051.PNG)


It is observed that the MAB Algorithm- "Thompson Sampling" proves more effective than A/B testing for this use case.
