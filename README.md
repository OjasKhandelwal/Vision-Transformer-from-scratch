# Vision-Transformer-from-scratch

Studied & Implemented the research paper “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale” in PyTorch using the MNIST dataset, achieving strong model accuracy.

# Code

So we divided our code in 3 parts

## 1. Patch Embedding :
This module splits an image into patches and then embeds each patch into a vector....basically converting the image into a sequence of tokens (like words in NLP), which can then be fed to a Transformer.

## 2. Transformer Encoder

This module processes the sequence of patch embeddings (from Part 1) and helps the model:

a. Learn global relationships between all patches (via Attention),

b. Build deeper representations (via MLP),

c. Maintain stability during training (via LayerNorm + Residual connections).

## 3. MLP Head For Classification

After the image has gone through:

Patch Embedding → (image → patch tokens)

Transformer Encoder → (learn relationships between patches)

we now have a sequence of embeddings, each representing part of the image.

The MLP Head converts this final representation into the class scores (logits).
for example: predicting whether the image is a “cat,” “car,” or “plane.”

![Architecture](ViT.png)



