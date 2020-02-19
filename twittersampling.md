---
title: Sampling Twitter Stream
---

# Sampling Twitter Stream: A Curated List

Sampling tweets from Twitter is not easy. This page lists papers and the sampling methods they used. Please contact me if you see there is any mistakes.

## Papers

- [Im, J., Chandrasekharan, E., Sargent, J., Lighthammer, P., Denby, T., Bhargava, A., ... & Gilbert, E. (2019). **Still out there: Modeling and identifying Russian troll accounts on Twitter. arXiv preprint arXiv:1901.11162.**](https://arxiv.org/abs/1901.11162)
    - Russian trolls
        - <span style="color:red">Official data.</span> 3841 accounts believed to be connected to the Internet Research Agency (IRA) released by Twitter. [Data](https://about.twitter.com/en_us/advocacy/elections-integrity.html#data)
        - <span style="color:red">Account based sampling.</span> Random sample of US-located users and ensured they tweeted at least 5 times between 2012-2017. Then randomly sampled 171291 of the these accounts. Then sample the most recent 200 tweets of each account (Used **total variation** method ([Compton, R., Jurgens, D., & Allen, D. (2014, October). **Geotagging one hundred million twitter accounts with total variation minimization.** In 2014 IEEE international conference on big data (big data) (pp. 393-401). IEEE.](https://arxiv.org/abs/1404.7152)) to geolocate all users)
        - <span style="color:red">Journalists' mentions.</span> Collected unseen accounts who have recently contacted high-profile political journalists on Twitter . High-profile journalists were selected from a pre-compiled [Twitter list](https://twitter.com/i/lists/15084461?lang=en). 

- [Zafar, M. B., Bhattacharya, P., Ganguly, N., Gummadi, K. P., & Ghosh, S. (2015). **Sampling content from online social networks: Comparing random vs. expert sampling of the twitter stream.** ACM Transactions on the Web (TWEB), 9(3), 1-33.](https://dl.acm.org/doi/abs/10.1145/2743023)

    - 


## Data