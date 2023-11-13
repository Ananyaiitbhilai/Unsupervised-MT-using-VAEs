# DS605 Assignment

**Authors:** Ananya (12040180), Vaibhav (12041650)

This Repo contains solution for DS605 (Deep Learning for low-resource NLP) assignment. This assignment basically revolves around building unsupervised machine translation system using discrete and continuous variance autoencoder models given certain subtasks to be taken into account.


## Assignment 
Assignment (50 Marks) What steps would you follow to build an unsupervised machine translation system using discrete and continuous variance autoencoder models? Additionally, deal with the subsequent sub-issues:

(i) What kind of encoding will this machine translation system utilize, and why? 

(ii) What kind of encoder-decoder model would be employed for this machine translation system, and why? 

(iii) What is the latent variable's expected loss value, and how will you define it? Hint: Although JS-divergence and Energy distance are both smooth functions and differentiable, KL-divergence is not.

(iv) Most text-VAE-based models do not support standard training methods such as backpropagation. Suggest some suitable approaches for training the model.

Bonus Point (50% of the assignment marks (25 Marks)): Design an unsupervised MT system that addresses the above-mentioned problems (and sub-problems) for the English-Hindi dataset. The submitted code will be evaluated based on metrics of performance (BLEU and TER).

---

## Solution
- Solution is in [this pdf of the repo][https://github.com/Ananyaiitbhilai/Unsupervised-MT-using-VAEs/blob/main/DS605_assignment1-2.pdf]
- Code is in [this file of the repo][https://github.com/Ananyaiitbhilai/Unsupervised-MT-using-VAEs/blob/main/DS605_Bonus_Question_Vaibhav_Arora_Ananya.ipynb]


## References

1. He, J. X. W., & Berg-Kirkpatrick, T. (2020). A Probabilistic Formulation of Unsupervised Text Style Transfer. ICLR.

2. Higgins, I., Matthey, L., Pal, A., Burgess, C., Glorot, X., Botvinick, M., ... & Lerchner, A. (2017). Beta-VAE: Learning basic visual concepts with a constrained variational framework. ICLR.

3. Bowman, S. R., Vilnis, L., Vinyals, O., Dai, A. M., Jozefowicz, R., & Bengio, S. (2016). Generating sentences from a continuous space. arXiv preprint arXiv:1511.06349.

4. Kingma, D. P., Salimans, T., & Welling, M. (2016). Improving variational inference with inverse autoregressive flow. NIPS.
