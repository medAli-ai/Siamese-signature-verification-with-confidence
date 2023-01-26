# Signature verification system using Siamese networks

Interesting Paper that deals with Classifying the Signatures as `forged` or `original` using Siamese Network

Siamese Neural Network is a class of neural network architectures that has two or more identical sub networks. The Sub Networks have same configuration with the same parameters and weights.

Parameter updating is mirrored across both sub networks.It is used find the similarity of the inputs by comparing its feature vectors.
*Triplet Loss*, *Euclidean Loss* or *contrastive loss* can be used to find the distance between the feature vectors.

Here, Cosine similarity is used for Pairwise Distance.


![Siamese Network](https://cdn-images-1.medium.com/max/800/1*LwOBbwGXMZUy6OzkFAPTzw.png)


## Data preprocessing

The functions in this notebook expect training data to be provided in a single .npz file, with the following components:

* ```x```: Signature images (numpy array of size N x 1 x H x W)
* ```y```: The user that produced the signature (numpy array of size N )
* ```yforg```: Whether the signature is a forgery (1) or genuine (0) (numpy array of size N )

We provide functions to process some commonly used datasets in the script ```sigver.datasets.process_dataset```. 
As an example, the following code pre-process the MCYT dataset with the procedure from [1] (remove background, center in canvas and resize to 170x242)

![Data preprocessing](https://github.com/medAli-ai/Siamese-signature-verification-with-confidence/blob/main/Images/processed.png)

During training a random crop of size 150x220 is taken for each iteration. During test we use the center 150x220 crop.

## Results
![Results](https://cdn-images-1.medium.com/max/800/1*LwOBbwGXMZUy6OzkFAPTzw.png)
