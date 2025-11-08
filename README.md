# Vision-Transformer-from-scratch

Studied & Implemented the research paper “An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale” in PyTorch using the MNIST dataset, achieving strong model accuracy.

# Code

So we divided our code in 3 main parts

## 1. Patch Embedding :
This module splits an image into patches and then embeds each patch into a vector....basically converting the image into a sequence of tokens (like words in NLP), which can then be fed to a Transformer.

## 2. Transformer Encoder

This module processes the sequence of patch embeddings (from Part 1) and helps the model:

a. Learn global relationships between all patches (via Attention),

b. Build deeper representations (via MLP),

c. Maintain stability during training (via LayerNorm + Residual connections).

## 3. MLP Head For Classification

After the image has gone through:

1. Patch Embedding : (image → patch tokens)

2. Transformer Encoder : (learn relationships between patches)

we now have a sequence of embeddings, each representing part of the image.

The MLP Head converts this final representation into the class scores (logits).
for example: predicting whether the image is a “cat,” “car,” or “plane.”


# How ViT Operates ??????

**Step 1**: Input an image.

**Step 2**: Split the image into fixed-size patches.

**Step 3**: Flatten each patch into a vector.

**Step 4**: Pass each flattened patch through a learnable linear layer to map it into a D-dimensional embedding.

**Step 5**: Add a learnable [CLS] token, which serves as a representation of the entire image.

**Step 6**: Add positional embeddings to retain patch order information.

**Step 7**: Feed the sequence (patch embeddings + [CLS] token) into the Transformer Encoder.

At this point, the [CLS] token embedding represents the overall image representation.

**Step 8**: Pass the [CLS] token embedding through the classification head (Linear layer + Softmax) to obtain the final class probabilities.






![Architecture](ViT.png)




# Thankyou :)
Thank you for reading the entire README and going through the code!

***Note***: ChatGPT was used solely for grammar correction. The content reflects my own understanding and interpretations of the original paper.

