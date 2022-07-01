Cell Neuclei Detection using Semantic Segmentation with U-Net

1. Summary

The aim of the project is to detect cell nuclei from biomedical images effectively. As cell nuclei vary in shapes and sizes, semantic segmentation proves to be the best approach to detect them. A deep learning model is trained and deployed for this task. The model is trained with the well known 2018 Data Science Bowl dataset.

2. IDE and Framework

The project is built with Spyder as the main IDE. The main frameworks used in this project are TensorFlow, Numpy, Matplotlib, OpenCV and Scikit-learn.

3. Methodology

The methodology is inspired by a documentation available in the official TensorFlow website. You can refer to the documentation here.

3.1. Input Pipeline

The dataset files contains a train folder for training data and test folder for testing data, in the format of images for inputs and image masks for the labels. The input images are preprocessed with feature scaling. The labels are preprocessed such that the values are in binary of 0 and 1. No data augmentation is applied for the dataset. The train data is split into train-validation sets, with a ratio of 80:20

3.2 Model Pipeline

The model architecture used for this project is U-Net. You can refer to the TensorFlow documentation for further details. In summary, the model consist of two components, the downward stack, which serves as the feature extractor, and upward stack, which helps to produce pixel-wise output. The model structure is shown in the figure below.

![model](https://user-images.githubusercontent.com/95268200/176823624-66f144ed-47cb-444c-82f4-e52a2164babc.png)

The model is trained with a batch size of 16 and 100 epochs. Early stopping is also applied in the model training. The training stops at epoch 24, with a training accuracy of 97% and validation accuracy of 96%. The model training graphs are shown in figures below.

![loss_graph](https://user-images.githubusercontent.com/95268200/176823640-a7f1e539-18b4-4556-995e-31cbc906937b.PNG)

![accuracy_graph](https://user-images.githubusercontent.com/95268200/176823653-4b091311-0828-4f70-9b84-03a5240c7c26.PNG)

The graphs show a clear sign of model convergence at an excellent convergence point.

4. Results

The model is evaluated with test data, which is shown in figure below.

![test_result](https://user-images.githubusercontent.com/95268200/176823713-6a28a157-ae61-4ce0-9c53-d06a3ee612c6.PNG)

Some predictions are also made with the model using some of the test data. The actual output masks and prediction masks are shown in figures below.

![prediction_1](https://user-images.githubusercontent.com/95268200/176823790-0082842c-aed5-44bf-bcf4-b19181e305be.PNG)

![prediction_2](https://user-images.githubusercontent.com/95268200/176823802-0c606a06-ecbe-4c2f-9208-1ec04c12615c.PNG)

![prediction_3](https://user-images.githubusercontent.com/95268200/176823820-b98b9469-b25b-41c3-a87d-25af92729c9c.PNG)

Overall, the model is capable of segmenting the cell neuclei with an excellent accuracy.
