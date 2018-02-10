# Sparse Networks in Keras
Keras Implementation of Sparse Networks from the paper [Sparsely Connected Convolutional Networks](https://arxiv.org/abs/1801.05895).

Code derived from the offical repository - https://github.com/Lyken17/SparseNet

# Sparse Networks
SparseNet is a variant of DenseNets. While DenseNets have a skip connection after every block in its dense structure, SparseNets have such skip connections only at depths of 2^N (with exponential offsets rather than a static linear offset). DenseNets posses *O(n^2)* skip connections for every dense block, whereas SparseNets have only *O(log n)* skip connections in each of its sparse blocks. 

This allows models which are **much less memory intensive**, while still performing at the level / even surpassing DenseNets, with fewer parameters. 

# Sparse Connectivity
<img src="https://github.com/titu1994/keras-SparseNet/blob/master/images/sparse_connectivity.PNG?raw=true" height="100%" width="100%">

The above image from the paper shows that each input at the end only requires *log2 n* input connections. 

# Difference between DenseNets and SparseNets
<img src="https://github.com/titu1994/keras-SparseNet/blob/master/images/dense_vs_sparse.png?raw=true" height="100%" width="100%">

This image from their paper shows the major difference between the connectivity pattern in SparseNets vs ResNets/DenseNets. 

# Caveats
There is a small discrepancy in the number of parameters between the paper and this repo.

- SparseNet-40-24 (Keras = 0.74 M, paper = 0.76 M)
- SparseNet-100-24 (Keras = 2.50 M, paper = 2.52 M)

If anyone can figure out the cause of this discrepancy, I'd be grateful.

# Requirements

- Keras 2.1.3
- Tensorflow / Theano / CNTK (I am assuming since all frameworks support ResNets, they should be able to support this as well without any modification)
