# Melanoma-Classfiercation
## Melanoma Classfiercation use Deep Learing

### Introduce 
Deep learning training is performed through CNN (Convolutional Neural Network) to classify benign and malignant melanocytoma images, improving the accuracy and reliability of doctors' diagnosis.
． Use image processing, data processing, amplification and other methods to make up for the problem of low accuracy of the CNN test set caused by overfitting.
． Training with Xception finally reached the AUC index of 95.27% for the training set and 83.18% for the validation set. Therefore, we judge that as long as we use       appropriate techniques to deal with the degradation of the model, the trained model can also perform well under the data set with unbalanced positive and negative     data and practical value.

### Data Preprocessing 
The data set obtained through Kaggle is a csv file. The main fields include patient number, gender, age, and diagnosis of benign or malignant tumors.
． The data needs to be pre-processed first, such as data cleaning, filling in missing values ​​and normalization, etc.
． Using the following image processing methods can make image features clearer and effectively prevent overfitting:
◎Data amplification
◎Gaussian blur
◎RGB to HSV

### Data Visualize 
1. Characteristics of human body parts![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/95cbb97c-e7a8-4784-8d74-d280fa144794)
2. Gender, age characteristics![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/8f8875a1-9c0a-4fbf-9804-b422fd420155)
3. Statistical number of benign and malignant tumors Age Gaussian distribution chart![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/14922723-c7da-44b7-85ec-f953505b5581)
4. Gender characteristics map of benign and malignant labels![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/9fc3c8d1-cd09-4982-bcb6-f51281d053a7)
5. Malignant label part feature map ![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/16f9df3a-6bd7-47dc-b94b-4c431d96be33)
6. Test dataset features ![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/d8099a70-9e96-493c-b411-ca90d3b94062)

### Image processing
1. Grayscale![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/ce73dbc7-1474-42b2-87d1-5be1c5eacfcb)
2. RGB to HLS color ![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/1f2fe4af-304b-4851-86f7-283122660db4)
3. RGB to HSV color![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/23db6902-9e1c-4af3-b13e-5a0e2e17357c)
4. RGB to HSV add Gaussian blur ![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/3b351fe9-ada4-49f2-b1ed-af23d5d87bf7)

### Xception Model 
1. Xception refers to the depthwiseseparable convolution technique, which first uses a 1x1 spatial pointwise conv operation, and then performs a depthwiseconv operation.![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/e96449bd-5038-4e97-b785-246962ea605b)
2. Xception's architecture contains 36 convolutional layers that form the feature extraction basis of the network.![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/5ffad924-4a3c-43fe-b5ee-3b2a18eca6b0)
3. `tf.keras.Sequential`
`base_model` -> GlobalAveragePooling
-> Dense(relu) -> Dense(sigmoid)
The output has dimension 1
●optimizer = Adam
      Loss function = binary crossentropy
   ![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/966567ab-e32f-4408-8535-8f7c257cb2c3)

### Weight adjustment
Passback model
 ． Increase the weight of malignant images.
 ． The model is scored based on the area under the line of the ROC curve.
     Define it as the AUC metric.![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/aa28189f-45d9-4a37-884a-44a4d0e7e6ce)
     ![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/4dbea50e-dce1-4a4c-94b3-f109828f5e4c)

### Achievements
![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/0269a3ea-dc68-4102-af93-fef4fa0d3dba)
![image](https://github.com/666jackson/Melanoma-Classfiercation/assets/113584996/7a6abfb2-a261-46ad-af4c-42fcd5c8b228)









