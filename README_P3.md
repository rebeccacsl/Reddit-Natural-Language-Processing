# Problem Statement
Subreddits is a popular discussion thread where millions of users with discussions on topics for specific thread. The high level number of discussions, questions and comments found in each specific subreddit results in a treasure cove of information. 

Statistics and Machine Learning are closely related topics. Statistics is also considered as a prerequisite to Machine Learning in terms of understanding the Machine Learning models. 

Hence this analysis aims to identify the correlation between Statistics and Machine Learning. Primary stakeholders could be aspiring Data Scientist who are interested to pick up the concepts and will like to find out if there is a strong correlation. Secondary stakeholders could be asipring statisticians who are interested to find out what way does statistics correlates with statistics. 

# References
Reference: https://machinelearningmastery.com/what-is-statistics/
    - Article discussed about the the relationship between Machine Learning and Statistics. 

# Data Source
The data source are extracted subreddit using the PRAW api. Due to limitations on the number of information that can be extracted, around 1000~ rows of information can be extracted per subreddit.

## Subreddit Link:
- Machine Learning: https://www.reddit.com/r/MachineLearning/
    - Extracted as "machine_learning_df.csv"
    - Contains data from machine learning subreddit.
- Statistics: https://www.reddit.com/r/statistics/
    - Extracted as "statistics_df.csv"
    - Contains data from statistics subreddit.

## Data Preprocessing Done:
As the purpose of this analyse is to identify whether there similarities between the posts, the key focus of the analysis will as follows:
 - "Title": Title of post
 - "Sub_Text": Additional information on post
 - "Comments": Comments to the post.

 Decision has been made to joined the three columns to better understand the overall content per post.

## Data Dictionary

|Feature               |Type          | Decription                                                          | 
|----------------------|------------------------------------------------------------------------------------|
|title                 |string object |Title of Subreddit Posts                                             | 
|sub_text              |string object |Additional description followed by Title. This field may be empty    |
|id                    |string object |Unique subreddit id of each post                                     |
|author                |string object |author of posts                                                      |
|score                 |int           |The number of upvotes for the submission                             |
|upvote_ratio          |float         |The percentage of upvotes from all votes on the submission           |
|comments_list         |string object |Extracted comments including the replies                             |
|datetime              |datetime      |datetime on when the post was posted.                                |
|year                  |int           |year information extracted from time.                                |
|month                 |int           |month information extracted from datetime.                           |
|joined_data           |string object |joined_data containing information from title, sub_text and comments |
|tokenize_join_comments|string object |tokenised with stopped wordsremoved from joined_data column          |
|is_ml                 |int           |1 and 0 indicates machine learning and statistics respectively       |

# Conclusion

The initial exploratory analysis using CountVectoriser revealed interesting insights on both the machine learning subreddit and statistics subreddit. The insights identified are as followed:

'data' and 'model'are words which are commently used both subreddit. 'data' has a higher count in statistics subreddit and 'model' has the higher count in machine learning subreddit.
'http' is a common term that is found within both subreddit but it is observed that that machine learning has more posts containing http indicating references to URLs.
It is observed that the discussion in the statistics revolved around statistics concepts and methods with references to statistical terms such as statistical terms such as 'mean','variable', 'statistics, 'hypothesis', 'linear'.

It is observed that coding is more closely related to the community such as 'github' and 'code'. Words such as 'chatgpt', 'gpt','openai', 'ai' indicates that artificial intelligence is a topic of interest within the community itself.

The machine learning community is also more active with more posts per month.

Results from Log Regression(TV) - M1 with an accuracy of 0.982 which only analyses the joined tokenised comments indicates that just from the discussion itself (e.g. title, sub_text, comments) contains sufficient unique features to distinguish post from one another.


## Recommendation
The currently insights is useful from the perspective of the primary stakeholders who could be people interested to move into the machine learning field as data scientist.

Insights from the post would be coding seems to be a relevant skill set.
Other insights would be Machine Learning and Statistics are similar in certain discussions but the topic discussed can still be accurately predicted for their respective thread. This implies that despite the perceived similarities, there are differences between the posts on the topics.

## Next Steps
1) Overcoming the limitations in the number of post retrieved to more than 1000 post with future libraries improvement:

Limitations from 1000~ post could affect the accuracy of analysis such as the trend of author activity within the same time period. Given that the machine learning subreddit is more active, 1000 post may contain only 2 months posts compared to statistiics which may have 3 months of post.
2) Further explore the models with different models such as KMeans to identify the relationships between the clusters.

3) Exploring the dataset in different ways such as:

segregating the comments and replies into different levels for analysis.
exploring the content of the reference link that are sent to find common topics of interest
exploring the community if there are active in both threads or only statistics or machine learning subreddit respectively.