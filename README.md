# Image Classification with Random Forest and SVM

## Project Overview
This project builds an image classification system using a small public image dataset stored in `images.zip`. The dataset contains five classes:

- dalmatian
- dollar_bill
- pizza
- soccer_ball
- sunflower

The workflow includes:
- loading image files
- resizing images to a uniform size
- normalizing pixel values
- splitting the dataset into training and testing sets
- training a Random Forest model with `GridSearchCV`
- evaluating the model using accuracy, precision, recall, and F1-score
- visualizing a confusion matrix
- visualizing feature importance
- predicting the class of a new image
- comparing Random Forest with SVM

## Files in this repository
- `image_classification_project.ipynb` - Google Colab notebook
- `report.pdf` - concise project report
- `report.docx` - editable version of the report
- `images.zip` - dataset
- `plots/` - generated figures used in the report

## Dataset
The dataset is a folder-based image dataset packaged as `images.zip`.  
Each class is stored in its own folder inside `images/`.

## Preprocessing
The notebook performs the following preprocessing steps:
1. Extracts the zip file
2. Loads images from class folders
3. Converts images to grayscale
4. Resizes images to 16 x 16 pixels
5. Normalizes pixel values to the range [0, 1]
6. Flattens each image into a feature vector
7. Splits the data into training and testing sets

## Models Used
### Random Forest
The Random Forest model is tuned with `GridSearchCV` using:
- `n_estimators`
- `max_depth`
- `min_samples_split`
- `min_samples_leaf`

**Best parameters found**
```python
{'max_depth': None, 'min_samples_leaf': 1, 'min_samples_split': 5, 'n_estimators': 100}
```

### Support Vector Machine (Bonus)
The SVM model is also tuned with `GridSearchCV`.

**Best parameters found**
```python
{'C': 10, 'gamma': 'scale', 'kernel': 'rbf'}
```

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

## Author Notes
This project was designed to satisfy a standard image classification assignment in a simple and readable way using plain Python, scikit-learn, and matplotlib.
