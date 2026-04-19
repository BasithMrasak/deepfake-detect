# DeepFake Image Detection

A deep learning web application that detects whether a face image is **Real** or **Fake** (AI-generated/manipulated). It uses MTCNN for face detection and a fine-tuned ResNet50 model for binary classification.

## How It Works

1. User uploads an image via the web interface
2. MTCNN detects and crops the face from the image
3. The cropped face is resized to 128×128 and normalized
4. A fine-tuned ResNet50 model predicts **Real** or **Fake**
5. Result is displayed on the result page

If no face is detected in the image, the app returns a "no face" response.

## Tech Stack

- **Model:** ResNet50 (fine-tuned, Keras `.h5`)
- **Face Detection:** MTCNN
- **Backend:** Flask (Python)
- **Frontend:** HTML, CSS, JavaScript
- **Image Processing:** OpenCV, PIL, scikit-image

## Project Structure
```
├── app.py                        # Flask app with upload, predict, result routes
├── model/
│   └── deepfake_resnet50.h5      # Trained model (not tracked in git)
├── static/
│   └── uploads/                  # Uploaded images stored here
├── templates/
│   ├── index.html
│   ├── upload.html
│   ├── result.html
│   └── 404.html
└── requirements.txt
```
## Setup & Run

```bash
# Install dependencies
pip install -r requirements.txt

# Run the app
python app.py
```

> **Note:** Place `deepfake_resnet50.h5` inside a `model/` directory before running.

## Model Details

- **Architecture:** ResNet50 (transfer learning)
- **Input Size:** 128 × 128 × 3
- **Classes:** Real | Fake
- **Face Extraction:** MTCNN (detects face bounding box before classification)


