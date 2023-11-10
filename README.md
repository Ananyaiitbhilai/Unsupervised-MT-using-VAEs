# Unsupervised-MT-using-VAEs
This Repo contains solutions for DS605 (Deep Learning for low-resource NLP) assignment. Assignment basically revolves around building unsupervised machine translation system using discrete and continuous variance autoencoder models given certain subtasks to be taken into account.


## Assignment 
Assignment (50 Marks) What steps would you follow to build an unsupervised machine translation system using discrete and continuous variance autoencoder models? Additionally, deal with the subsequent sub-issues:

(i) What kind of encoding will this machine translation system utilize, and why? 

(ii) What kind of encoder-decoder model would be employed for this machine translation system, and why?

(iii) What is the latent variable's expected loss value, and how will you define it? Hint: Although JS-divergence and Energy distance are both smooth functions and differentiable, KL-divergence is not.

(iv) Most text-VAE-based models do not support standard training methods such as backpropagation. Suggest some suitable approaches for training the model.

Bonus Point (50% of the assignment marks (25 Marks)): Design an unsupervised MT system that addresses the above-mentioned problems (and sub-problems) for the English-Hindi dataset. The submitted code will be evaluated based on metrics of performance (BLEU and TER).

## Solution


### Code
Code for the bonus question is in folder named ```code```. The ```READme.md``` file in that folder contains the instructions, evaluation and results.


## References
[1] [UNSUPERVISED MACHINE TRANSLATION USING MONOLINGUAL CORPORA ONLY](https://openreview.net/pdf?id=HJlA0C4tPS)
[2] [A PROBABILISTIC FORMULATION OF UNSUPERVISED TEXT STYLE TRANSFER](https://openreview.net/pdf?id=HJlA0C4tPS)
[3] [Fully Unsupervised Machine Translation Using Context-Aware Word Translation and Denoising Autoencoder](https://www.tandfonline.com/doi/epdf/10.1080/08839514.2022.2031817?needAccess=true)
[4] [Unsupervised Transfer Learning in Multilingual Neural Machine Translation with Cross-Lingual Word Embeddings](https://www.semanticscholar.org/paper/Unsupervised-Transfer-Learning-in-Multilingual-with-Mullov-Pham/395221cd3ff22539f261ef1fc305fa3e928fca35)
[5] [Unsupervised Neural Machine Translation for English and Manipuri](https://www.semanticscholar.org/paper/Unsupervised-Neural-Machine-Translation-for-English-Singh-Singh/1c99e76a9446d311f4a70c808b7825b5f22df1a6)
[6] [Variational Autoencoding Neural Operators](https://www.semanticscholar.org/paper/Variational-Autoencoding-Neural-Operators-Seidman-Kissas/296b76cfec5e19899c823ddcce5347f956d84845)
