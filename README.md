# 📷 Age-Prediction-Supermarket

This project focuses on developing a deep learning model to predict a person's age from images, aiming to assist the "Good Seed" supermarket chain in adhering to alcohol sales laws. The goal is to prevent underage sales by accurately identifying the age of customers at checkout.

### Data Overview
- The dataset consists of 7591 images of faces, each labeled with the `real_age`.
- Ages range from 1 to 100 years, with a mean age of approximately 31.2 years, indicating a diverse age distribution suitable for training a robust model.
- Image data is preprocessed to 150x150 pixels with 3 color channels and scaled pixel values between 0.0 and 1.0.

### Model Development
- A deep learning model based on the **ResNet50** architecture (pre-trained on ImageNet) was developed for regression, using `raw` age labels.
- The model was trained with `ImageDataGenerator` for data augmentation (horizontal flip) and image preprocessing.
- The optimizer used was `Adam` with a learning rate of 0.0005, and the loss function was `Mean Squared Error (MSE)`, with `Mean Absolute Error (MAE)` as the evaluation metric.

### Results and Conclusions
- The model was trained for 20 epochs on a GPU platform.
- It achieved a **validation MAE of 6.9743** at Epoch 20, which is below the project's requirement of an MAE not higher than 8.
- While the model demonstrated good learning, an increasing gap between training MAE and validation MAE suggested some degree of overfitting. This means the model performed better on seen data than on unseen validation data.
- **Limitations:** Despite meeting the MAE requirement, an average prediction error of nearly 7 years is not precise enough to strictly comply with alcohol sales laws (e.g., distinguishing between 17 and 18-year-olds). It is much more reliable and easy just to compare the id passport photo to the customer's face.

### Potential Future Improvements
- Further hyperparameter tuning.
- Exploring more advanced data augmentation techniques.
- Investigating different model architectures or ensemble methods to improve generalization and reduce overfitting.
- The model could potentially be refined for other practical applications, such as marketing segmentation at checkout.
