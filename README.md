# Road-Marking-Extraction-U-Net
Semantic Segmentation of Road Markings from Aerial Images using U-Net Architecture

**BACKGROUND**
For this purpose of this project, annotated aerial images were sourced. The images were captured from a 3K camera system consisting of three Canon Eos 1Ds Mark III cameras which was used for recording the raw data. Two dataset types were used in this project: Skyscapes Multi- Lane and Skyscapes Dense. In total, 20 representative RGB images of size 5616 × 3744 pixels were chosen. The flight height of about 1000 m above ground led to a GSD of approximately 13 cm. The images depict urban and partly rural areas with highways and first/second order roads. Complex traffic situations like crossings and congestions are included.

**Skyscapes Dense**: This dataset consists of aerial images with 20 coloured classes.
**Skyscapes Multi-Lane**: This dataset consists of aerial images with 13 lane marking coloured classes.
**Dataset Source**: Downloads – EOC – datasets (dlr.de)


**METHODOLOGY**
A U-Net model is implemented for aerial image semantic segmentation using TensorFlow and Keras in Python. U-Net is a convolutional neural network architecture designed for image segmentation tasks. The model is trained to classify each pixel in an image into one of several predefined classes, creating a segmented output that highlights specific features of interest in the aerial images. The implementation involved loading and preprocessing the training data, which includes image patching into 805 patches per image, resizing, and categorizing the images into specific classes. The U-Net architecture is defined using Keras, consisting of contraction and expansive paths for feature extraction and reconstruction. The model is compiled with the Adam optimizer and categorical crossentropy loss. Training is performed on the prepared dataset with specified callbacks for saving the best model, early stopping, and logging training metrics. The training metrics for the U-Net model are displayed over 50 epochs, providing insights into the model's performance on both the training and validation sets. Each epoch reports the loss, accuracy, IoU coefficient, and Jaccard index for both training and validation. The code also includes functions for post-processing, such as one-hot encoding masks, reshaping images, and creating a binary segmentation problem. Additionally, there are utility functions for visualizing image classes with colour legends. Finally, the model is trained, saved, and loaded for predictions, with visualizations showing the input aerial image, ground truth, and the model's segmentation prediction.

**RESULTS**
In Epoch 1, the model starts with a loss of 1.8705 and an accuracy of 35.20%. The IoU coefficient and Jaccard index are relatively low at 0.1469. As training progresses, the metrics gradually improve. The model demonstrates increased accuracy and better segmentation performance, as indicated by higher IoU coefficients and Jaccard indices. Notably, the validation accuracy also improves over epochs, reaching 71.53% in the final epoch (Epoch 20). Training callbacks are used to monitor and save the best model based on the validation accuracy. For instance, in Epoch 5, there is a notable improvement in validation accuracy from 56.73% to 62.58%, leading to the saving of model weights. 
In Epoch 15 and Epoch 20, the model continues to improve, reaching a validation accuracy of 70.32% and 71.53%, respectively, and the weights are saved. Overall, the training metrics indicate a successful training process with a consistentimprovement in the model's ability to segment lane marking as well as other classes from aerial images. As seen in the images, lane markings are labelled as dark orange while other classes are also visibly labelled. This provides opportunity for multi-class extraction.

**REFERENCES**
1. [1803.06904] Aerial LaneNet: Lane Marking Semantic Segmentation in Aerial Imagery using 
Wavelet-Enhanced Cost-sensitive Symmetric Fully Convolutional Neural Networks (arxiv.org)
2. ad-1/u-net-aerial-imagery-segmentation: Semantic Segmentation of MBRSC Aerial Imagery 
of Dubai Using a TensorFlow U-Net Model in Python (github.com
