# Image Labeler using Amazon Rekognition

A Python project that uses Amazon Rekognition to analyze an image stored in Amazon S3 and detect labels such as people, animals, objects, and scenes.

## Overview

This project demonstrates how to:

- upload an image to an S3 bucket
- configure AWS credentials and region
- call Amazon Rekognition's `DetectLabels` API
- display the image and label the detected objects

It is a simple and beginner-friendly example of integrating AWS AI services with Python.

## Features

- Detects labels from an image using Amazon Rekognition
- Prints detected labels and confidence scores
- Displays the source image with bounding boxes
- Uses Python libraries such as `boto3`, `matplotlib`, and `Pillow`

## Tech Stack

- Python 3
- Amazon S3
- Amazon Rekognition
- AWS CLI
- `boto3`
- `matplotlib`
- `Pillow`

## Prerequisites

Before running the project, make sure you have:

- Python 3 installed
- AWS account with access to Amazon Rekognition and S3
- AWS CLI configured
- An S3 bucket containing the image file

## Project Structure

```text
Image-Labeler-using-Amazon-Rekognition/
├── image_labeler.py
├── requirements.txt
├── example_image.png
├── README.md
└── .gitignore
```

## Installation

1. Clone the repository:

```bash
git clone https://github.com/Abhay0018/Image-Labeler-using-Amazon-Rekognition.git
cd Image-Labeler-using-Amazon-Rekognition
```

2. Create and activate a virtual environment (optional but recommended):

```bash
python -m venv .venv
.venv\Scripts\activate
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

## AWS Setup

Configure AWS credentials and region:

```bash
aws configure
```

Set your region to match the bucket location, for example:

```bash
us-east-1
```

Or set it manually in the terminal:

```powershell
$env:AWS_DEFAULT_REGION = "ap-south-1"
```

Also make sure your IAM user has permissions for:

- `rekognition:DetectLabels`
- `s3:GetObject`

You can attach policies such as:

- `AmazonRekognitionFullAccess`
- `AmazonS3ReadOnlyAccess`

## Upload the Image

Upload an image like `example_image.png` to your S3 bucket and ensure the bucket name and object key match the values in `image_labeler.py`.

By default, the script uses:

```python
photo = 'example_image.png'
bucket = 'image-labeler-using-rekognition-bucket'
```

## Run the Project

```bash
python image_labeler.py
```

On Windows, if `python` is not found, use:

```powershell
py image_labeler.py
```

## Expected Output

The script will print detected labels and confidence values, such as:

```text
Detected labels for example_image.png

Label: People
Confidence: 100.0

Label: Dog
Confidence: 86.5
```

It will also display the image with bounding boxes around detected objects.

## Notes

- This project requires a valid AWS configuration.
- Do not commit AWS access keys or secret keys to GitHub.
- Keep your AWS credentials in local environment variables or your AWS CLI config only.

## License

This project is for educational and demonstration purposes.
