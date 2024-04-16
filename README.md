<h1 align="center" id="title">Tom and Jerry Videos Screen Time Calculator</h1>

<p id="description">This project is a screen time calculator for the characters Tom and Jerry implemented using OpenCV and deep learning. It detects and tracks the characters Tom and Jerry providing statistics on their screen time in the video</p>

<h2>Project Screenshots:</h2>

<img src="https://github.com/Samarth1410/Tom-and-Jerry-Video-Screentime-Calculator/blob/master/Training%20Frames/frame100.jpg" alt="project-screenshot" width="400" height="400/">

<img src="https://github.com/Samarth1410/Tom-and-Jerry-Video-Screentime-Calculator/blob/master/Output%20Screen.png" alt="project-screenshot" width="400" height="400/">

  
  
<h2>🧐 Features</h2>

Here're some of the project's best features:

*   Import and read the video extract frames from it and save them as images
*   Label a few images for training the model (Don’t worry I have done it for you)
*   Build our model on training data
*   Make predictions for the remaining images
*   Calculate the screen time of both TOM and JERRY

<h2>🤔Challenges Faced</h2>

*   First, I tried using the pretrained model without removing the top layer. The results were not satisfactory. The possible reason could be that these are the cartoon images and our pretrained model was trained on actual images and hence it was not able to classify these cartoon images. To tackle this problem, i retrained the pretrain model using few labelled images and the results were better from the previous results.

*   Even after training on the labelled images, the accuracy was not satisfactory. The model was not able to perform well on the training images itself. So, i tried to increase the number of layers. Increasing the number of layers proved to be a good solution to increase the training accuracy but there was no sync between training and validation accuracy. The model was overfitting and its performance on the unseen data was not satisfactory. So I added a Dropout layer after every Dense layer and then there was good sync between training and validation accuracy.

*   I noticed that the classes are imbalanced. TOM had more screen time so the predictions were dominated by it and most of the frames were predicted as TOM. To overcome this and make the classes balanced, i used compute_class_weight() function of sklearn.utils.class_weight module. It assigned higher weights to the classes with lower value counts as compared to the classes with higher value counts.

*   I also used Model Checkpointing to save the best model, i.e. the model which produced lowest validation loss and then used that model to make the final predictions.  
  
<h2>💻 Built with</h2>

Technologies used in the project:

*   Python
*   Deep Learning
*   OpenCV
