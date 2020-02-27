---
title: Sampling Twitter Stream
---

# Sampling Twitter Stream: A Curated List

Sampling tweets from Twitter is not easy. This page lists papers and the sampling methods they used. Please contact me if you see there is any mistake. 

## Introduction

Twitter supplies 10% random sampled tweets for a fee, and 1% randomly sampled tweets for free. The exact details of how these samples are selected are not made public by Twitter. It is claimed by [Twitter API documentation](https://developer.twitter.com/en/docs) that they are random samples of all public tweets. (Probably we can do an experiment to test? XD)



## Methodology papers
- [Zafar, M. B., Bhattacharya, P., Ganguly, N., Gummadi, K. P., & Ghosh, S. (2015). **Sampling content from online social networks: Comparing random vs. expert sampling of the twitter stream.** ACM Transactions on the Web (TWEB), 9(3), 1-33.](https://dl.acm.org/doi/abs/10.1145/2743023)
    - About
        - This paper compares random tweet samples with tweets sampled from a small group of "expert users".
        - expert tweets contain larger and more refined information. They are also more popular and trustworthy.(As expected)
        - expert tweets catches breaking news and important events earlier than randomly sampled tweets.
        - the opinion mining results from the two types of samples matches.
        - *sampling spam* in the Twitter random samples, that is, some users deliberately tweeting more in order to have a greater presence in the randomly sampled streams
        
    - Sampling schemes
        - <span style="color:red">Random sampling</span>  Paper mentioned that most studies using Twitter data today rely on the 1% and 10% randomly sampled streams fo tweets that are provided by Twiitter.
        - <span style="color:red">Expert sampling</span> Only sample so called expert users on a wide range of topics. Over half a million experts are identified, using a crowd-source expert dection proposed in [Ghosh, S., Sharma, N., Benevenuto, F., Ganguly, N., & Gummadi, K. (2012, August). **Cognos: crowdsourcing search for topic experts in microblogs.** In Proceedings of the 35th international ACM SIGIR conference on Research and development in information retrieval (pp. 575-590).](https://people.mpi-sws.org/~gummadi/papers/twitter_wtf.pdf) Basically, they rank Twitter users by their List-rank matric that is related to the number of times a user is listed. This is more robust to spammers/link farmers than follow-links in Twitter. (weighted list-rank matric could be better? If we assign weights to lists?)
    - Comparing samples
        - Many characteristics are used.
        - Pearson product-moment correlation coefficient,  Jaccard score, and latent Dirichlet allocation model.

- [Morstatter, F., Pfeffer, J., & Liu, H. (2014, April). **When is it biased? Assessing the representativeness of twitter's streaming API.** In Proceedings of the 23rd international conference on world wide web (pp. 555-556).](https://dl.acm.org/doi/abs/10.1145/2567948.2576952)
    - About
        - Find bias in the free 1% sample from Twitter's streaming API by Twitter's Sample API.
        - In the paper, a hashtag is “biased” if the relative trend is statistically significantly over-represented or underrepresented in contrast to its true trend on Twitter.
    - Comparing samples
        - comparing the ranks of top hashtags (Kendall's \\( \tau \\) score), as well as the occurances of hashtags.
    

- [Morstatter, F., Pfeffer, J., Liu, H., & Carley, K. M. (2013, June). **Is the sample good enough? comparing data from twitter's streaming api with twitter's firehose. In Seventh international AAAI conference on weblogs and social media.**](https://arxiv.org/abs/1306.5204)
    - About
        - Find bias in the free 1% sample from Twitter's streaming API by Twitter's Firehose.
    - Comparing samples
        - Comparing the ranks of top hashtags (Kendall's \\( \tau \\) score), as well as the occurances of hashtags. 
        - LDA topical models and Jenson-Shannon divergence.
        - Network measures. (Node-level as well as network-level)
        - Geographical measures. (e.g. proportions of tweets from different locations) 


- [Rafail, P. (2018). **Nonprobability sampling and Twitter: Strategies for semibounded and bounded populations.** Social Science Computer Review, 36(2), 195-211.](https://journals.sagepub.com/doi/pdf/10.1177/0894439317709431)
    - About
        - The implication of different sampling strategies on overall data quality.
        - Conceptual distinctions between four types of populations. 
            - Twitter as a data source. 
            - unbounded population. (Random sampling is better)
            - semibounded population (user-restricted or topic-restricted). 
            - bounded population (user-restricted and topic-restricted).
        - Suggests more comperhensive data collecting strategies and compared the results via empirical data.
        - Hashtag samples (samples collected from a small set of hashtags) misrepresent important aspects of Twitter activity and may lead to erroneous conclusions.

    - Sampling schemes
        - Sampling unbounded populations.
            - random sampling 
        - Sampling user-restricted semibounded populations
            - Step one: a comprehensive list of the accounts of interest
            - Step two: collect all tweets posted by each account. 
            - Step three: oscillate between these steps as new accounts become identified.
        - Sampling topic-restricted semibounded populations
            - When discussion is rela-tively limited in its frequency or in applications when the words used to describe a topic aredynamic, the Search API may produce better coverage; however, when the content is generatedquickly or using a stable set of key words, the Streaming API may be preferable.
        - Sampling bounded populations
            - Step one: first create a database of the accounts of interest
            - Step two: collect all tweets posted by each account. 
            - Step three:  the results from the user time lines can be pareddown so that only tweets matching the topics of interest are retained.

    - Comparing samples
        - trands in hashtag usage.


## Applied Papers

- [Im, J., Chandrasekharan, E., Sargent, J., Lighthammer, P., Denby, T., Bhargava, A., ... & Gilbert, E. (2019). **Still out there: Modeling and identifying Russian troll accounts on Twitter. arXiv preprint arXiv:1901.11162.**](https://arxiv.org/abs/1901.11162)
    - About
        - Russian Trolls
    - Sampling schemes
        - <span style="color:red">Official data.</span> 3841 accounts believed to be connected to the Internet Research Agency (IRA) released by Twitter. [Data](https://about.twitter.com/en_us/advocacy/elections-integrity.html#data)
        - <span style="color:red">Account based sampling.</span> Random sample of US-located users and ensured they tweeted at least 5 times between 2012-2017. Then randomly sampled 171291 of the these accounts. Then sample the most recent 200 tweets of each account (Used **total variation** method ([Compton, R., Jurgens, D., & Allen, D. (2014, October). **Geotagging one hundred million twitter accounts with total variation minimization.** In 2014 IEEE international conference on big data (big data) (pp. 393-401). IEEE.](https://arxiv.org/abs/1404.7152)) to geolocate all users)
        - <span style="color:red">Journalists' mentions.</span> Collected unseen accounts who have recently contacted high-profile political journalists on Twitter . High-profile journalists were selected from a pre-compiled [Twitter list](https://twitter.com/i/lists/15084461?lang=en).



## Data

- Twitter official list of malicious activities [Data](https://about.twitter.com/en_us/advocacy/elections-integrity.html#data)

## People

[Fred Morstatter](https://isi.edu/~fredmors/)