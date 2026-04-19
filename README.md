What I Did
1. Preprocessing
Loaded the images
Resized them to a consistent size
Normalized pixel values
Split data into training and testing sets
2. Model Training
Used Random Forest with GridSearchCV to find the best parameters
Trained the model using the best settings
3. Model Evaluation
Measured:
Accuracy
Precision
Recall
F1-score
Created a confusion matrix to see where the model made mistakes
4. Feature Importance
Visualized which pixels were most important for predictions
5. SVM Comparison (Bonus)
Trained an SVM model
Compared results with Random Fores

## Results
### Random Forest
- Accuracy: 0.7097
- Precision: 0.7436
- Recall: 0.7097
- F1-score: 0.7053

### SVM
- Accuracy: 0.6452
- Precision: 0.6694
- Recall: 0.6452
- F1-score: 0.6481

## How to Run in Google Colab
1. Upload `image_classification_project.ipynb` to Google Colab
2. Upload `images.zip` into the Colab working directory
3. Run all cells in order
4. Review the output metrics, confusion matrices, and plots

## Deployment Strategy
A practical deployment strategy would be:
- save the trained model with `joblib` or `pickle`
- expose prediction through a simple Flask or FastAPI API
- allow users to upload an image
- apply the same preprocessing steps used in training
- return the predicted class label
- deploy on a cloud platform such as Azure, AWS, or Google Cloud

