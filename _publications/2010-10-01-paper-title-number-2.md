---
title: "Apply Real-time Vicinal Defense make the Robust Recommendation"
collection: publications
excerpt: "First author. The paper proposes an attack-agnostic and model-agnostic defense against poisoning attacks in recommender systems. We also conduct a theoretical bound about the unlearning strength. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href='/publication/2010-10-01-paper-title-number-2' target='_blank' style='color: #007bff; text-decoration: none; font-size: 20px;'>details...</a>"
date: 2023-11-15
permalink: /publication/2010-10-01-paper-title-number-2
submitted: 1
venue: 'AAAI'
preprint: https://arxiv.org/abs/2309.17278
preprinted: 1
---
* First author. &nbsp;Supervisor: Prof. Defu Lian, USTC.
* Contribution: We propose Real-time Neighborhood Defense (RVD) to enhance the robustness of the model. During the inference phase, for each user, we select its neighbors and fine-tune the model on them. This is an unlearning process, and we theoretically guarantee its unlearning strength. Our approach can effectively defend against different poisoning attacks on different models. By applying our method on other defenses, we can further improve their robustness.
* Challenges:
  * In the experiment, it was necessary to test the recommendation effectiveness of the NSVD model. At that time, the hit@k metric was used, requiring obtaining ratings for all users on all items. However, the prediction formula for NSVD is as follows: $$\hat{r}_{ui}=b_u+b_i+\sum_{j\in R_u}p_jq_u^T$$. Based solely on the formula, predicting ratings for each user and item sequentially was time-consuming. Thus, there was an urgent need for a batch prediction formula. The first two terms of the formula could be accelerated using TensorFlow's broadcasting mechanism. The focus was on the summation term. Initially, for each user $u$, it was noticed that $\sum_{j\in R_u}p_j$ could be precalculated. Then we can multiply the precalculated matrix $P'$ by the transpose of the user feature matrix, $Q^T$ to get predicted ratings of all users on all items. The next task was to efficiently preprocess $P$ to obtain $P'$. Upon observation, it was found that $P'$ was essentially the result of a matrix multiplication with $P$, where this matrix served as a mask for the interaction matrix: $M_{ui}=1$ if and only if user $u$ had a rating on item $i$. As a result, the summation term could be rewritten as $PM^TQ^T$, effectively solving the problem of batch prediction.
  * Theoretical derivation of unlearning strength: The current objective is to prove that, after removing certain data points, the distance between the model parameters trained on the new dataset and the optimal parameters remains within a certain range. I found that this distance can be magnified by a factor of the distance between the parameters obtained from training on the old dataset and the optimal parameters on the new dataset. Thus, it can be further bounded using the triangle inequality into the sum of the distance between the parameters obtained from training on the old dataset and the optimal parameters on the old dataset, and the distance between the optimal parameters of the new and old datasets, both of which have existing theoretical limits. Combining these aspects results in a theoretical guarantee for the forgettable learning capability.

