# Neural_net_19

## preprocessing 

After importing the data I looked to make 3 major preprocessing moves. The first being the removal of unneeded columns and the second and third being cutting down on columns to that all catagorical columns have no more than 10 unique values. The first step was removing the "name" and the "EIN" columns from the data frame as they are not required to make predicitons and shoudldnt be hot encoded.The second was to check the numer of unqiue objects in the columsn using ".nunique()" , and identifiying " APPLICATION_TYPE" and " CLASSIFICATION" as needing to be paired down before hot encoding. TO do this I first checked the value_count() of the column, created a replace object which was a list of anything that had less than the choosen amount for that column to cut down on enteries. I then looped through the replacement object list and replaced everything in the column that was in the list with an "Other" to have no more than ten unique enteries in each column. 

# hot encoding 
I next used SKlearn.preprocessing - oneHotEncoder to create and transform the catagorical columns inside the data set. With the new Encoded dataFrame I merged it to the orinal data set and dropped the original catagorical columns for the hot encoded ones. 

# train test split 
next the data was split into the X array which dropped the "IS_SUCCESFULL" column  and Y which was only an array for the "IS_SUCCESFULL" column. Once this was completed the train_test_split was done. 

The X_train and X_test objects were both scaled before being inputed into the model. 

# defining model 
I tried multiple different set ups for the model and got ver simular results from different models. I concluded that more preproccesing or more nodes could hopefully increase the accuary of the model. The first model used 45 input features( number of columns in the x_scaled_train) and 8 nodes in the first hidden layer. The total number of parameters was 393. After compiling and fitting the X_train_scaled with 50 epochs the loss was 218701 and the accuracry was .533 when compared to the X_test data. I condluded the model needed to be compared to the X_Test_Scaled and when I did that I found the loss to be .57 and the accuracry to be .72 . So with just one hidden RELU layer the model was able to get close to 75 % accuracy. 


I then tried two layers instead of one with 8 neurons each in the hopes of increasing accuracy and reducing loss. The loss was almost the same and the accuracy was the same.

I then tried 16 and 16 neurons and found there to be no change again. 

I then tried increasing the training data to 85 % and found no increase to the accuracry. 

I think less cutting down of the columns could increase the data given to model to see if it could get find a way to be more accuracte. 

