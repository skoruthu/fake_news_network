README

Using Github (https://github.com/KaiDMML/FakeNewsNet) repository allows one to download the data that will be similar to the dataset shared. For Twitter policy restrictions this entire dataset is not made public.

FakeNewsNet contains fake and real news pieces from the Politifact and GossipCop news sources.

The dataset is labeled as fake and real and news pieces are placed in the following folders,

a) politifact_fake : This folder contains the fake news pieces from Politifact dataset
b) politifact_real : This folder contains the real news pieces from Politifact dataset
c) gossipcop_fake : This folder contains the fake news pieces from GossipCop dataset
d) gossipcop_real : This folder contains the real news pieces from GossipCop dataset


Each news piece contains news content and social context information. User details are gathered in directories irrespective of news labels and the news source since multiple news articles can be shared by the same user. Only 5000 users details are sampled and their details are provided for the sharing purpose since the number of users is large and requires more storage space.

News Content:
-------------
news content.json: This json includes all the meta information of the news articles collected using the provided news source URLs. This is a JSON object with attributes including:

text of the body of the news article.
a list of the URLs of all the images in the news article web page.
the date that news article is published.


Social Context :
---------------
tweets folder: This folder contains all tweets related to the news sample. This contains the tweet objects of the all the tweet ids provided in the tweet_ids attribute of the dataset csv. All the files in this folder are named as <tweet_id>.json . Each <tweet_id>.json file is a JSON file with format mentioned in https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/tweet-object.html.

retweets folder: This folder contains the retweets of the all tweets posted sharing a particular news article. This folder contains files named as <tweet_id>.json and it contains a array of the retweets for a particular tweets. Each object int the retweet array have format mentioned in https://developer.twitter.com/en/docs/tweets/post-and-engage/api-reference/get-statuses-retweets-id.

likes folder: This folder contains details of the users liking all the tweets posted sharing a particular article. This folder contains files named as <tweet_id>.json and has JSON array of users ids who liked a particular tweet. 

replies folder: This folder contains the comments and chain of replies to the tweets posted related for a news piece. Each file in this folder is named as <tweet_id>.json and has JSON data of the reply information including the reply content, time of reply, user_id replying.

User information:
----------------

user_profiles folder: This folder contains all the user profiles of the users posting tweets related to all news articles. This same folder is used for both datasources ( Politifact and GossipCop). It contains files named as <user_id>.json and have JSON formated mentioned in https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/user-object.html

user_timeline_tweets folder: This folder contains files representing the time line of tweets of users posting tweets related to fake and real news. All files in the folder are named as <user_id>.json and have JSON array of upto 200 recent tweets of the users. The files have format mentioned same as https://developer.twitter.com/en/docs/tweets/timelines/api-reference/get-statuses-user_timeline.html.

user_followers folder: This folder contains all the user followers ids of the users posting tweets related to all news articles. This same folder is used for both datasources ( Politifact and GossipCop). It contains files named as <user_id>.json and have JSON data with user_id and followers attributes.

user_following folder: This folder contains all the user following ids of the users posting tweets related to all news articles. This same folder is used for both datasources ( Politifact and GossipCop). It contains files named as <user_id>.json and have JSON data with user_id and following attributes.