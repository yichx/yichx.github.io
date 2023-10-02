---
title: "Poisoning Federated Recommendation Using Fake Users"
collection: publications
permalink: /publication/fedrec_poison
excerpt: "Co-first author. This paper proposes a poisoning attack on federated recommender systems based on fake users that require no extra knowledge or local training data. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href='/publication/fedrec_poison' target='_blank' style='color: #007bff; text-decoration: none; font-size: 20px;'>details...</a>"
submitted: 0
venue: 'UseNix'
date: 2023-10-15
preprinted: 0
---
* Co-first author. &nbsp;Supervisor: Prof. Neil Zhenqiang Gong, Duke University.
* Contribution: Federated recommendation attack based on fake users. Conducting effective attacks with each fake client having no knowledge of any additional information, the attack's impact surpasses even the baseline where the attacker possesses partial extra information.
* Key idea: I aim to construct a target model that can assign high ratings to a specific target item. In each round of the attack, fake clients can send model updates to the server, pulling the embedding of the target item towards the target model. However, the attacker lacks any information about other user features. Given an item embedding, they cannot directly assess its popularity; they must indirectly obtain the target model. A natural idea is to first guess which items are more popular, then construct the embedding of the target item based on the embeddings of these items. The method ultimately used involves averaging these embeddings, resulting in an embedding that predicts positive ratings for most users. When scaled by a coefficient, the ratings are magnified, leading to the recommendation of the target item to these users. Regarding estimating the popularity of items: I examined embeddings of items with varying popularity and identified features that ensure the highest popularity. Ultimately, I found that estimating the top-k popular items can be achieved by finding the item embeddings with the smallest dot product with the average embedding.

