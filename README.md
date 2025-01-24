# Image Recommendation System

This project is a **Image Recommendation System** that classifies a given image into one of three categories and retrieves 10 similar images from Google. The main steps include image classification using a convolutional neural network (CNN) and web scraping to find similar images.

## Features
- **Image Classification**: Trains a CNN model to classify images into predefined categories.
- **Google Image Search**: Searches Google for similar images based on the category of the uploaded image.
- **Image Retrieval and Display**: Downloads and displays the recommended images.

## Dataset
The dataset used for this project includes three categories of products:
1. Bottle of gym
2. Coffee mug
3. Stein beer glass

You can add more categories by expanding the dataset.

## Technologies Used
- **TensorFlow/Keras**: For building and training the image classification model.
- **OpenCV**: For image preprocessing.
- **Requests & BeautifulSoup**: For web scraping Google Images.
- **Matplotlib**: For displaying the recommended images.

## Setup
Follow these steps to set up and run the project:

### Prerequisites
Install the required libraries:
```bash
!pip install opencv-python opencv-python-headless opencv-contrib-python matplotlib tensorflow requests beautifulsoup4
```

### Dataset Preparation
1. Upload a zipped dataset of images organized into training and validation folders.
2. The folder structure should look like this:
```
Products/
  Train/
    Bottle of gym/
    Coffee mug/
    Stein beer glass/
  Valid/
    Bottle of gym/
    Coffee mug/
    Stein beer glass/
```

### Running the Project
1. Upload the dataset using:
   ```python
   files.upload()
   ```
   Extract the zip file:
   ```python
   zipRef = zipfile.ZipFile('/content/Products.zip', 'r')
   zipRef.extractall()
   zipRef.close()
   ```

2. Preprocess the images:
   ```python
   for name in root:
       ... # Resize and save images
   ```

3. Train the model:
   ```python
   model.fit(training_fluxo, epochs=12, validation_data=validation_fluxo)
   ```

4. Upload an image for classification and recommendation:
   ```python
   SystemRecommendationImages()
   ```

5. Display the recommended images:
   ```python
   for child in os.listdir('/content/downloaded_images'):
       ...
   ```

## How It Works
1. **Image Classification**:
   - The CNN model classifies the uploaded image into one of the predefined categories.

2. **Google Search**:
   - Using the predicted category, a Google Image search is performed to find 10 similar images.

3. **Image Downloading**:
   - The system downloads the images and saves them in a folder structure based on the category.

4. **Visualization**:
   - The downloaded images are displayed using Matplotlib.

## Example Output
For an uploaded image of a "Coffee mug", the system:
1. Predicts the category as "Coffee mug".
2. Searches Google Images for similar coffee mugs.
3. Downloads and displays 10 images of coffee mugs.

## Limitations
- The project uses a basic Google Image scraping method which may not be stable due to changes in Google's policies or structure.
- The model is limited to the predefined categories and their dataset quality.

## Future Improvements
- Expand the dataset to include more categories.
- Enhance the CNN model with transfer learning.
- Use a more robust method for web scraping or integrate with an API for image search.
- Add user interface for easier interaction.

## Acknowledgments
- TensorFlow/Keras Documentation
- OpenCV and Matplotlib for image processing and visualization
- BeautifulSoup for web scraping
