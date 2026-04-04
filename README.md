# Autoencoder From Scratch

This project is a notebook-based implementation of a simple fully connected autoencoder for the MNIST dataset. It trains a PyTorch model to compress handwritten digits into a low-dimensional latent representation, reconstruct the input images, and visualize the learned embedding space.

## What It Does

- Loads the MNIST dataset with `torchvision`
- Trains a feed-forward autoencoder in PyTorch
- Reconstructs input digits and plots original vs. reconstructed images
- Extracts latent vectors from the encoder
- Visualizes the latent space with Matplotlib or Plotly
- Computes a silhouette score to estimate class separation in latent space
- Generates digits from random latent vectors using the decoder

## Project Files

- [autoencoder_from_scratch.ipynb](autoencoder_from_scratch.ipynb): main notebook containing the model, training loop, and visualizations
- [requirements.txt](requirements.txt): dependency list for running the notebook

## Requirements

- Python 3.9 or newer
- PyTorch
- torchvision
- numpy
- matplotlib
- scikit-learn
- plotly

If you have a CUDA-compatible GPU, PyTorch will use it automatically. Otherwise, the notebook runs on CPU.

## Setup

Create and activate a virtual environment, then install the dependencies listed in `requirements.txt`.

```bash
pip install -r requirements.txt
```

If you prefer to install packages manually, make sure the libraries listed above are available in your environment.

## How To Run

1. Open [autoencoder_from_scratch.ipynb](autoencoder_from_scratch.ipynb) in Jupyter or VS Code.
2. Run the notebook cells from top to bottom.
3. Let MNIST download into the local `./data` folder the first time you run it.
4. Review the printed training loss, reconstruction plots, latent-space plots, and the silhouette score.

## Model Overview

The notebook defines a compact autoencoder with:

- An encoder that maps flattened 28x28 images into a latent vector
- A decoder that reconstructs the image from that latent vector
- ReLU activations in the hidden layers
- A sigmoid output layer to keep reconstructed pixel values in the $[0, 1]$ range

The model is trained with mean squared error loss and the Adam optimizer.

## Outputs

When you run the notebook, you should see:

- Training loss printed for each epoch
- A side-by-side comparison of original and reconstructed MNIST digits
- A 1D, 2D, or 3D latent-space visualization, depending on the latent dimension
- A silhouette score for the learned embeddings
- A sample reconstruction generated from a random latent vector

## Notes

- The notebook is intended as an educational example rather than a production training pipeline.
