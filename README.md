# Study and Implementation of the Grad-CAM algorithm
📚 "Computer Vision" project (Artificial Intelligence, UniGe)

In this project we try to classify two different classes of images through a CNN and then we introduce Grad-CAM, a class-discriminative localization technique that generates visual explanations for any CNN-based network without requiring architectural changes or re-training. 

## What is it?
Grad-CAM is a technique for producing ‘visual explanations’ for decisions from a large class of Convolutional Neural Network (CNN)-based models, making them more transparent and explainable. Grad-CAM uses the gradient information flowing into the last convolutional layer of the CNN, which have the best compromise between high-level semantics and detailed spatial information, to assign importance values to each neuron for a particular decision of interest. The result is that produce a coarse localization map highlighting the important regions in the image for predicting the concept.

## How does it work?
From a high-level, we take an image as input and create a model that is cut off at the layer for which we want to create a Grad-CAM heat-map. We attach the fully-connected layers for prediction. We then run the input through the model, grab the layer output, and loss. Next, we find the gradient of the output of our desired model layer w.r.t. the model loss. From there, we take sections of the gradient which contribute to the prediction, reduce, resize, and rescale so that the heat-map can be overlaid with the original image. 

![gradcam](https://miro.medium.com/max/1400/1*zq1lp5Bg8sdflG_ngrezzg.png)

## Why do we use it?
In the context of image classification models, our visualizations lend insights into failure modes of these models (showing that seemingly unreasonable predictions
have reasonable explanations), are robust to adversarial perturbations, are more faithful to the underlying model, and help achieve model generalization by identifying dataset bias.

## More information:
For more details you can check out the [academic paper](https://arxiv.org/pdf/1610.02391.pdf) which outlines the complete mathematics.
