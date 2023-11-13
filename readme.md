# DS605 Assignment

**Date:** \today

**Authors:** Ananya (12040180), Vaibhav (12041650)

---

## Table of Contents

- [Problem Statement](#problem-statement)
- [Problem Statement Formulation](#problem-statement-formulation)
- [Building Unsupervised Machine Translation with VAEs](#building-unsupervised-machine-translation-with-vaes)
- [Answer to Sub-Parts](#answer-to-sub-parts)

---

## Problem Statement

The problem is to build an unsupervised machine translation system using discrete and continuous variance autoencoders. The key aspects include:

- Unsupervised setting with no parallel data.
- Use of variational autoencoders (VAEs) with discrete and continuous latent variables.
- Translation from source to target language and vice versa.
- Challenges in modeling discrete sequences and non-differentiable training.

...

---

## Building Unsupervised Machine Translation with VAEs

### 1. Preprocessing

Preprocess the monolingual corpora in the source and target languages to tokenize, clean, and normalize the data.

### 2. Language Model Training

Train source and target language models on the monolingual data to serve as priors in the VAE framework.

...

### Variational Autoencoder (VAE)

VAEs learn deep generative models defined by a prior \(p(z)\) and a conditional distribution \(p_\theta(x|z)\). The marginal likelihood \(p(x)\) is intractable, so VAEs optimize the evidence lower bound (ELBO):

\[
L(x;\theta,\phi) = \mathbb{E}_{z \sim q_\phi(z|x)}[\log p_\theta(x|z)] - \beta \text{KL}(q_\phi(z|x) || p(z))
\]

where ...

---

## Answer to Sub-Parts

### Answer i: Encodings

...

### Answer ii: Encoder-Decoder Model

...

### Answer iii: Latent Variable Loss

...

### Answer iv: Training

...

---

## References

1. He, J. X. W., & Berg-Kirkpatrick, T. (2020). A Probabilistic Formulation of Unsupervised Text Style Transfer. ICLR.

2. Higgins, I., Matthey, L., Pal, A., Burgess, C., Glorot, X., Botvinick, M., ... & Lerchner, A. (2017). Beta-VAE: Learning basic visual concepts with a constrained variational framework. ICLR.

3. Bowman, S. R., Vilnis, L., Vinyals, O., Dai, A. M., Jozefowicz, R., & Bengio, S. (2016). Generating sentences from a continuous space. arXiv preprint arXiv:1511.06349.

4. Kingma, D. P., Salimans, T., & Welling, M. (2016). Improving variational inference with inverse autoregressive flow. NIPS.
