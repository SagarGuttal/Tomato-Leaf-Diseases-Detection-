# Tomato Leaf-Diseases Detection :-
## Description
* The  enhancement and advancement  in  agricultural technology  and  the  use  of  artificial  intelligence  in diagnosing  plant  diseases,  it  becomes  important  to  make pertinent  research  to  sustainable  agricultural development.  Various  diseases  like  early  blight  and  late blight immensely influence the quality and quantity of the tomatos and  manual  interpretation  of  these leaf diseases is  quite  time-taking  and  expensive.  As  it  requires tremendously  a  good  level  of  expertise,  efficient  and automated  detection  of  these  diseases  using technology can  assist the formers to  potato  crop production.  
* Diseases in Plants are  a  major concern to  the  farmers these days.  Many  a  times, the  farmers  are  not sure which pesticide or insecticide is needed to  treat a  particular  diseased  plant  because they are not sure of the type of disease. This results in spraying wrong pesticides, damaging the plants which affect the plant yield. To  overcome  with  this  problem,  we  have  come  up  with  a  solution  of  developing  a  system  that easily identifies some common diseases that occur in a tomato plant by merely examining the leaves of the plants. These diseases are: **Tomato_Early_blight', 'Tomato_Late_blight', 'Tomato_healthy'** Through image processing and Deep learning technique, our aim to classify such diseases and generate  a  model  that  would  provide  an  easy  and  accurate  way  of  determining  the  plant  disease through on click of an image of the affected plant leaf. This system is not only beneficial to the farmers in saving the crops, but also in  saving money by buying only right kind of pesticides suitable to treat the particular disease.  

## Steps taken for this projects :-
1. Image collection
2. Image preprocessing
3. Spliting image features and corresponding labels (Classes)
4. Dividing image dataset into training set, Validation set, testing set,
5. Creating CNN (convolutional neural network) --> deep learning technique
6. Training phase of neural network
7. Evaluatate neural network with testing set
8. Save the model

## Image collection :-
* All class diseses images are dowloaded in kaggle website
* Dowload Image dataset [click here](https://www.kaggle.com/datasets/emmarex/plantdisease).
* Created separate directory where i downloaded all images 
* Sturuture of directory ---> Tomato images
                                - Late blight leaf
                                - Early blight leaf
                                - Healthy leaf
* Loaded the image dataset directory to tensorflow using **"tf.keras.preprocessing.image_dataset_from_directory"** API's.
* sample images

![sample images](https://github.com/SagarGuttal/Tomato-Leaf-Diseases-Detection-/blob/main/Images/Sample%20images%20from%20dataset.png)


## Image preprocessing :-
* All collected images are not as size and pixcel so that preprocessing of images are important.
* Image dataset contains **4568 images** of 3 different classes and these images are loaded it into 32 images for each batch.
Three classes are -> **'Tomato_Early_blight', 'Tomato_Late_blight', 'Tomato_healthy'.**
* Image size ----> **256,256,3,** , Batch_size ----> **32**
* This step involves processing the  test image in order to bring it to the size, colour and quality of the images  comprising  our  dataset.  This  involves  various  stages  through  which  the  image  goes.  
* These stages are: 
   1. Image Resizing:  The dimensions of the image are brought equal to the dimensions of the training images by using the computer vision cv2.resize method, Image resizing is a crucial step as the pixel values may change if the dimensions of all the training as well as the testing images are not the same. 
   2. Image rescaling: The  smoothening of the image renders the pixel values to  gradually  even  out  to  all the points of the image so as to allow  a smooth image. Along with this the image also gets converted from colored to grayscale image using the function „RGB2GRAY ()‟. 
   3. Noise  Filtering: The noise is the unwanted extras that  are  present in  the  images that make feature determination  and  extraction  difficult.  Thus  the  process  of  noise  filtering  involves  removal  or averaging of the  pixel  values that  add  noise to the  image. The process  used  in our system  to  ensure noise removal is Median Filter.
   4. Data augmentation: Data augmentation is the technique of increasing the size of data used for training a model. For reliable predictions, the deep learning models often require a lot of training data, which is not always available. Therefore, the existing data is augmented in order to make a better generalized model
   5. Some images are removed by manually.
   

## Splitting images into training, validation, testing set
* 80 % of Images set goes for training
* 10 % of Images set goes for validation
* 10 % of Images set goes for testing our final model
* Total 144 batches of datasets having total 4568.
* we take 114 batches of dataset for training (114 * 32)
* Ramaining dataset for testing and validation ()
* we take 14 batches for validation (14*32)
* we take 14 bathces for final testing(14*32)

## Convolutional Neural Network
* A convolution is the simple application of a filter to an input that results in an activation. Repeated application of the same filter to an input results in a map of activations called a feature map, indicating the locations and strength of a detected feature in an input, such as an image.
* Using tensorflow API's added the convolutional layers with 16 filters of (3*3) and also added maxpooling layer with "Relu" activation and padding and strides also
* After that CNN layers added ANN layers.
* I used "Adam" opimizer for updating the weights of each neurons.
* Summary of neural network

![Summary of CNN](https://github.com/SagarGuttal/Tomato-Leaf-Diseases-Detection-/blob/main/Images/Model%20summary.png)

* After CNN creted load of training images to train the model.
* After training is done evaluate model using tesing images.
* Check the model performace.

## Model performance
*  Accuracy of model with training images and testing images
![Accuracy of model](https://github.com/SagarGuttal/Tomato-Leaf-Diseases-Detection-/blob/main/Images/model%20accuracy.png)

* Accuracy Loss of model with training images and testing images
![Loss of model](https://github.com/SagarGuttal/Tomato-Leaf-Diseases-Detection-/blob/main/Images/model%20loss.png)
