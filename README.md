# Content-Based-Image-Retrieval

## Overview
This project focuses on implementing a Content-Based Image Retrieval (CBIR) system. The system utilizes various image features and pattern recognition techniques to identify and retrieve images from a database that are similar to a given target image. The project includes tasks involving global and local feature extraction, histogram matching, texture analysis, and deep neural network embeddings.

## Features
Global Features
Global features describe the entire image, providing information on color, shape, and texture. Examples include:
Color histograms
Color moments
Shape descriptors
Local Features
Local features capture visual patterns or structures in small regions of an image, such as: Edges, Points, Image patches

## Tasks
Task 1: Baseline Matching
Description: Navigate a database to find images similar to a target image using classic features and distance metrics.
Method: Extract a 7x7 pixel square from the image center, compute the L2 norm (Euclidean distance) between these baseline features.

Task 2: Histogram Matching
Description: Use HSV color space to compute histogram features for an image.
Method: Convert image to HSV, compute histograms for H and S channels with 8 bins each, normalize histograms, reshape into a 1xN matrix.

Task 3: Multi-Histogram Matching
Description: Utilize whole image and center region histograms for matching.
Method: Compute histograms for H and S channels, use a custom distance metric with histogram intersection and weighted average distance.

Task 4: Texture and Color Matching
Description: Combine texture and color features for matching.
Method: Compute gradient magnitude using Sobel operators, create histograms of gradient magnitudes, combine with color histograms for matching.

Task 4 Extension: Advanced Texture Matching
Laws Texture Matching: Apply Laws' masks to grayscale images, compute energy values from convolutions, and use Euclidean distance for matching.
Gabor Filters: Use Gabor filters to extract textural properties, concatenate responses, and match based on histogram separations.
Fourier Transform: Compute the magnitude spectrum of the Fourier Transform, resize, normalize, and use for matching.

Task 5: DNN Embeddings
Description: Utilize deep neural network embeddings for image matching.
Method: Extract feature vectors from the final average pooling layer of a pre-trained ResNet18 model, use sum-square distance and cosine distance for matching.

Task 6: Comparing Classic Features vs DNN
Description: Compare the effectiveness of classic features and DNN embeddings.
Observations: DNN embeddings capture high-level semantic information and complex patterns, while classic features are computationally efficient and suitable for smaller datasets.

Task 7: Shape and Feature Detection
Description: Combine DNN features with Sobel gradients for image retrieval.
Method: Compute cosine similarity between feature vectors, calculate Sobel gradients, combine similarities for final score.
