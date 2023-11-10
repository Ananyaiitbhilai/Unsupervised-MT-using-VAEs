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

Here are the steps I would follow to build an unsupervised machine translation system using discrete and continuous latent variable autoencoder models:

1. Preprocess the monolingual corpora in the source and target languages. This includes tokenization, normalization, handling of rare words, etc.

2. Train continuous latent variable autoencoders (e.g. VAEs) separately on the source and target monolingual corpora. The encoder maps sentences to continuous latent representations and the decoder reconstructs the original sentences. The latent space should capture semantic features.

3. Train discrete latent variable autoencoders (e.g. VQ-VAE) separately on the source and target monolingual corpora. The discrete latent space allows for cross-domain alignment.

4. Initialize the shared latent space using the continuous latent representations from step 2. Align the discrete latent representations from step 3 in this shared space using adversarial training.

5. Train a shared encoder to map source and target sentences into the aligned shared latent space.

6. Train a shared decoder to reconstruct/translate sentences from the shared latent representations.


### Answer to sub-parts

1) I would use a bidirectional LSTM encoder to encode the source sentence into a dense vector representation. LSTMs can capture long-term dependencies in sequences and bidirectional encoding gives access to both past and future context when encoding each word. The machine translation system will utilize a shared continuous-discrete hybrid latent space. The discrete latent variable autoencoder model would be used to obtain a compressed representation of the sentences in the source language, while the continuous latent variable autoencoder model would be used to obtain a compressed representation of the sentences in the target language. The continuous representation captures semantics while the discrete space enables alignment. This combination allows for the modeling of both discrete and continuous aspects of the language data.

2) I would use an attentional LSTM decoder because attention provides an alignment between source and target words. This helps focus the model on relevant parts of the source when generating each target word. LSTMs have been shown to be effective seq2seq decoders. I choose this attentional sequence-to-sequence model because it provides an alignment between source and target phrases through the attention mechanism, while both the encoder and decoder can model linguistic context and long-range dependencies. This architecture has proven effective for machine translation. The attention mechanism allows the model to focus on different parts of the input sentence when generating the output sentence, which is particularly useful for machine translation tasks where the length and complexity of the input and output sentences can vary widely. I also think an attentional encoder-decoder model like the Transformer would also be suitable, with multi-layer encoders and decoders. This provides representational power for complex translations.

3) For the continuous VAE, I would use the KL divergence between the posterior encoder distribution q(z|x) and the prior p(z) as the loss for the latent variable z. For the discrete VAE, since KL divergence is not differentiable, I would use an alternative loss like JS divergence or energy distance. [The paper](https://openreview.net/pdf?id=HJlA0C4tPS) also introduces a negative entropy term in the KL loss term to encourage the posterior distribution to be more spread out, which helps to prevent the model from overfitting to the training data.

4) For the discrete VAE, standard backpropagation is not possible due to the non-differentiable sampling operation. I would use the REINFORCE algorithm which uses Monte Carlo sampling from the encoder and rewards from the decoder to train the model. The Gumbel-Softmax relaxation is another option that provides a continuous approximation to categorical sampling for backpropagation. 
One approach can also be using the reparameterization trick, which involves sampling from a noise distribution and transforming the samples using a differentiable function to obtain samples from the posterior distribution. This allows for the use of backpropagation to compute gradients and update the model parameters. Another approach is to use the Gumbel-Softmax estimator or REINFORCE algorithm to approximate the gradients of the ELBO objective. Additionally, [the paper](https://openreview.net/pdf?id=HJlA0C4tPS) suggests using a stop-gradient method to approximate the gradients of the reconstruction loss, which has been shown to be more effective than other gradient estimation methods.

In summary, I would use an attentional LSTM encoder-decoder model with a bidirectional encoder. For the continuous VAE, I would use the KL divergence loss, while for the discrete VAE, I would replace it with a smooth alternative and use Reinforce or Gumbel-Softmax for training.

### Code
Code for the bonus question is in folder named ```code```. The ```READme.md``` file in that folder contains the instructions, evaluation and results.


## References
[1] [UNSUPERVISED MACHINE TRANSLATION USING MONOLINGUAL CORPORA ONLY](https://openreview.net/pdf?id=HJlA0C4tPS)

[2] [A PROBABILISTIC FORMULATION OF UNSUPERVISED TEXT STYLE TRANSFER](https://openreview.net/pdf?id=HJlA0C4tPS)

[3] [Fully Unsupervised Machine Translation Using Context-Aware Word Translation and Denoising Autoencoder](https://www.tandfonline.com/doi/epdf/10.1080/08839514.2022.2031817?needAccess=true)

[4] [Unsupervised Transfer Learning in Multilingual Neural Machine Translation with Cross-Lingual Word Embeddings](https://www.semanticscholar.org/paper/Unsupervised-Transfer-Learning-in-Multilingual-with-Mullov-Pham/395221cd3ff22539f261ef1fc305fa3e928fca35)

[5] [Unsupervised Neural Machine Translation for English and Manipuri](https://www.semanticscholar.org/paper/Unsupervised-Neural-Machine-Translation-for-English-Singh-Singh/1c99e76a9446d311f4a70c808b7825b5f22df1a6)

[6] [Variational Autoencoding Neural Operators](https://www.semanticscholar.org/paper/Variational-Autoencoding-Neural-Operators-Seidman-Kissas/296b76cfec5e19899c823ddcce5347f956d84845)
