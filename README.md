# dog-vision

<p align = "center">
<img src ="https://user-images.githubusercontent.com/86231828/125239967-c64e0480-e32c-11eb-81a4-5ee0fb85e20a.jpg" width=auto height="200">
</p>

## An end-to-end project predicting dog breeds from images.

This repository stores an end-to-end deep-learning Jupyter workbook which utilizes transfer learning from the pre-trained neural architecture [MobileNet V2](https://tfhub.dev/google/imagenet/mobilenet_v2_130_224/classification/4) and deep-learning to classify a dog breed from a prescribed image.  The notebook was edited and computed on Google's [Colab](https://colab.research.google.com/), and it is _**highly recommended**_ that you do so as well to utilize a GPU backend, thereby making training about 30x quicker (30 minutes for full training set of 10,000+ images, which you can find [here](https://www.kaggle.com/c/dog-breed-identification/)). The final, fully trained model have been uploaded here as well.

### Abstract

I developed a multi-class classifier model using the MobileNet V2 architecture (see above) and further added 120 trainable dense layers, one for each unique dog breed in the training data. In order to utilize MobileNet V2, I had to preprocess all the images into tensors which had a resolution of 224 x 224 entries, necessary for input into MobileNet V2, and then further create batches of 32 images to more optimally train the model. For training, I chose a cross-entropy loss function and the Adam optimizer and included a callback which enacted an early stop if the accuracy did not appreciably change in 3 epochs to ensure that the model did not overfit the training data. In total, the model was trained on 10,222 images of dogs over a span of 33 minutes before early termination.

### Results

Here's an example of the model predicting the most likely dog breed for some custom test images.

<p align="center">
<img src="https://user-images.githubusercontent.com/86231828/125240031-e2ea3c80-e32c-11eb-8459-fbef774d8f58.jpg" width=auto height="250">
</p>

The notebook can also return the top 10 most likely dog breeds as well.

<p align="center">
<img src="https://user-images.githubusercontent.com/86231828/125259759-f86a6100-e342-11eb-9c54-87db9d10f46e.jpg" width=1000 height=auto>
</p>
