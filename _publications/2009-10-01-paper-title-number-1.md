---
title: "Robust Federated Learning Mitigates Client-side Data Reconstruction Attacks"
collection: publications
permalink: /publication/2009-10-01-paper-title-number-1
excerpt: "First author. &nbsp;I have proposed the adaptive attack using PGD, conducted all experiments, and written the entire paper. &nbsp;Supervisor: Prof. Neil Zhenqiang Gong, Duke University. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href='/publication/2009-10-01-paper-title-number-1' target='_blank' style='color: #007bff; text-decoration: none; font-size: 20px;'>details...</a>"
venue: 'NDSS'
submitted: 1
date: 2023-06-28
---
* First author. &nbsp;I have proposed the adaptive attack using PGD, conducted all experiments, and written the entire paper. &nbsp;Supervisor: Prof. Neil Zhenqiang Gong, Duke University.
* Contribution: We verified that known defense measures are not effective in defending against data reconstruction attacks in federated learning. To address this, a simple yet effective approach is proposed: after users upload model updates, the server calculates the coordinate-wise median and only selects model updates within a certain range from the median based on their distance. This range is determined by the l2 norm of the median. In addition to this defense, we also propose an adaptive attack using PGD to disguise the attacker's model update, which can partially weaken the defense effect but the defense remains effective.
* Key idea: when I was trying to design an advanced reconstruction attack and wanted to find a defense that can mitigate the original data reconstruction attack, it was found that there were no effective defense methods. Therefore, I turned to find an effective defense approach. It was discovered that aggregation rules like median can limit the strength of the attack but cannot completely eliminate it, resulting in the gradual improvement of the attack over time. As a result, the idea of leveraging the robustness advantage of model updates obtained through median was conceived, aiming to find the **entire** model update that is close to the median. This would allow for accurate and thorough rejection of model updates from attackers.
* Speculations for future research: I have observed that many current theoretical advancements regarding the robustness of federated learning focus on security aspects, such as whether the model's performance or predictions can be arbitrarily influenced by malicious users. However, there is limited theoretical investigation into privacy concerns, particularly whether the model could potentially leak user data. This should be a worthwhile direction to explore in future studies.

