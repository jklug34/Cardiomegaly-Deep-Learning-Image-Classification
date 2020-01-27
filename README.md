# Cardiomegaly-Deep-Learning-Image-Classification
Trained a deep learning model with attention mechanism to classify NIH Chest X-rays for Cardiomegaly (enlarged heart) 


Background: 
Cardiomegaly or enlarged heart is not a disease, but a sign of another underling condition.  An enlarged heart may be due to short-term stress on the body, pregnancy, weakening of the heart muscle, coronary artery disease, heart valve problems or abnormal heart rhythms. People with an enlarged heart may have no signs or symptoms or others might have shortness of breath, abnormal heart rhythm, or swelling (edema).  There are 200,000+ cases diagnosed every year.  

Some underlying causes may include:
High blood pressure
Heart valve disease
Cardiomyopathy
Pulmonary Hypertension (high blood pressure in artery connecting heart and lungs)
Pericardial effusion (fluid around the heart)
Coronary heart disease
Anemia
Thyroid disorders
Hemochromatosis (excessive iron in the body)
Amyloidosis

Prevention: 
Controlling high blood pressure with diet and exercise and possible medications
Controlling risk factors for coronary artery disease (tobacco use, high blood pressure, high cholesterol and diabetes)


An enlarged heart can be seen on a chest x-ray.  Utilized over 112,000 chest x-ray images from more than 30,000 unique patients from a deidentified NIH database.  
https://www.kaggle.com/nih-chest-xrays/data

A deep learning model that classifies cardiomegaly was trained. It used a VGG16 model trained on ImageNet data and retrained it on grayscale chest x-ray images.  Additionally, an attention model was used to mask unimportant parts of the image facilitating learning for an enlarged heart.  


### Example data frame
Example of raw data.  There are 14 different disease classes in the "finding lables" column plus a "No Finding".  
![example_dataframe](https://user-images.githubusercontent.com/48166327/73209973-2a134c00-40fe-11ea-95a8-fa2b8903fa68.png)


### Raw data distributions
Only 2.48% (2776/112120) of the images had a classification of cardiomegaly.   
![distributions_raw](https://user-images.githubusercontent.com/48166327/73209997-37303b00-40fe-11ea-8e0a-8f8f84934c2a.png)


### Balance data distribution
Due to the imbalance between cardiomegaly and non-cardiomegaly images (unbalanced datasets are harder to train).  The dataset was rebalanced non-cardiomegaly: cardiomegaly 3:1 (so 25% of the images were positive for cardiomegaly)
![distributions_rebalance](https://user-images.githubusercontent.com/48166327/73210068-5c24ae00-40fe-11ea-9f80-2764f7caae9b.png)


### Example cardiomegaly chest x-ray images versus control
![example_images_cardiomegaly](https://user-images.githubusercontent.com/48166327/73210136-7f4f5d80-40fe-11ea-8d81-8983885dc988.png)


### Data was randomly split into training, validation and test datasets
![split_train_val_test](https://user-images.githubusercontent.com/48166327/73217014-f7705000-410b-11ea-9186-9d7788ebb00c.png)


### Overall model architecture
![model_architecture](https://user-images.githubusercontent.com/48166327/73210214-a4dc6700-40fe-11ea-8c55-2e5cd448f11b.png)


### Model Training
![Training_epoch_10](https://user-images.githubusercontent.com/48166327/73217025-fc350400-410b-11ea-945b-1f27d951b4cb.png)
![training_epoch_greater_10](https://user-images.githubusercontent.com/48166327/73217032-00f9b800-410c-11ea-95bd-ed12c6549f9d.png)


### Example image attention model heat map
![example_attention_heat_map](https://user-images.githubusercontent.com/48166327/73210335-e8cf6c00-40fe-11ea-8730-c5676e263e91.png)


### Confusion matrix following testing
![confusion_matrix](https://user-images.githubusercontent.com/48166327/73210377-0270b380-40ff-11ea-9a43-da261efc0168.png)


### Classification scoring 
![classifacation_report](https://user-images.githubusercontent.com/48166327/73210443-28965380-40ff-11ea-8b77-fbf40184efcb.png)


### ROC curve
![ROC_curve](https://user-images.githubusercontent.com/48166327/73210461-32b85200-40ff-11ea-9503-1d5a11133569.png)


