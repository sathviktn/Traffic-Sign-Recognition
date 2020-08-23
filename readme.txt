Traffic Sign Recognition

 Hello everyone . This is a traffic sign recognition project which is created using deep learning and CNN and it is coded in jupyter notebook and the dataset is from kaggle website.

 In this project, We have used 43 different classes of traffic signs for classifying. 
 we are using numpy for creation of array of images, pandas for reading the csv file,matplotlib for plots, pillow for image processing, tensorflow for backend, cv2, keras and sklearn libraries are also required.
 
 Initially we open the directory where the dataset is stored and open every image and resize them. Each image is appended to the data list and the corresponding classes are appended to the labels list.
 Now we create numpy arrays of these lists. we then split the dataset into 80% as train and 20% as test dataset.
 now the class labels for train and test dataset are converted into one hot encoding using to_categorical() into 43x43 vector representation.
 The model we are building is sequential model. Conv2D creates 2D convolutional kernal which takes kernel size of (5,5)(dimensions of kernal for processing the image) and activation function as relu which is REctified Linear Unit is a max function which sets all negative values to zero and other values constant as arguments.
 
 Maxpool2D reduces image dimensionality and here pool_size is (2,2) which is window size of 2x2
 Dropout is used to ignore some of the neurons(data points) randomly from the dataset while fitting the model. It used to handle overfitting of the model. 
 Flatten() is used to convert nD array to 1D array.
 activation function softmax is used when we have to build multiclass classifier.
 Compiling of the model is done by categorical_crossentropy as loss for the parameter. categorical cross entropy is used to minimize the distance between predicted and actual class label. optimizer adam is used to find individual learning rate for each parameter .
 An epoch is the number of times the iteration takes place to fit the model. model is fitted for the trained dataset in a batch size of 32 images.
 
 we are using matplotlib for the plotting of graphs between epochs and accuracy for training accuracy and validation accuracy  and also between epochs and loss for training loss and validation loss.  As u can see the validation accuracy is higher than the training accuracy, since we dont use dropout for validation set. 
 Testing the model using the test dataset and finding accuracy score using scikit learn.
 predict_classes uses trained model for predicting the images of the test dataset. 
 Tkinter is used as front-end for this project and it is an built-in library of python.
 We have created python dictionary for 43 classes of traffic signs.
 we have created the upload button for uploading the image and after pressing the button, the upload function is called. In turn, a new dialog window appears where we have to choose the image for the prediction and open it. 
 We have classify button for predicting the class for the uploaded image. as you can see the classify function is called and it uses the model for predicting the class. and displays the class label. 
