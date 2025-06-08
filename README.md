# Dockerized Fashion MNIST

This project provides a dockerized solution for deploying a Fashion MNIST model. It includes a trained model, an API for predictions, and a Jupyter Notebook for training.

---

## 📁 Project Structure

```
.
├── app/
│   ├── trained_model/
│   │   ├── trained_fashion_mnist_model.h5
│   │   └── trained_fashion_mnist_model_new.keras
│   ├── Dockerfile
│   ├── main.py
│   └── requirements.txt
├── model_training_notebook/
│   └── Fashion_MNIST_model_training.ipynb
├── test_images/
├── venv/
├── .gitignore
└── README.md
```

---

## Setup Instructions
Prerequisite

Ensure that Docker Engine is installed and running on your system before proceeding.


### 1. Clone the Repository

```bash
git clone https://github.com/AtharvaSangit/dockerized-fashion-mnist.git
cd dockerized-fashion-mnist
```

### 2. Install Dependencies (For Local Use)

```bash
pip install -r app/requirements.txt
```

### 3. Build Docker Image

```bash
cd app
docker build -t fashion-mnist-app .
```

### 4. Run the Docker Container

```bash
docker run -p 8501:8501 fashion-mnist-app
```

### 5. API Usage

Once the container is running, make a POST request to:

```
http://localhost:5000/predict
```

with a test image file.

---

## 🧠 Model Details

* **Dataset:** Fashion MNIST
* **Frameworks Used:** TensorFlow / Keras
* **Training:** Done via Jupyter Notebook


## Solution Overview & Evaluation

### Approach to Solve the Problem

The goal of this project is to build a deployable solution for Fashion MNIST classification. The overall approach involved:

### Model Development:

Used a Convolutional Neural Network (CNN) architecture trained on the Fashion MNIST dataset.

Training was performed using TensorFlow and Keras within a Jupyter Notebook.

### Model Export:

The trained model was saved in both .h5 and .keras formats to ensure compatibility with different deployment scenarios.

### Deployment:

Created a Dockerized solution for both Streamlit-based UI.

Encapsulated the model inference logic in main.py.

### Containerization:

Docker was used to package the application, ensuring platform independence and easy distribution.

Dockerfile installs dependencies, copies model and app code, and sets the entry point for execution.


## Tools/Libraries Used

TensorFlow/Keras – for model building and training.

Streamlit – for interactive UI deployment.

Docker – for containerization and deployment.

Jupyter Notebook – for iterative model development and experimentation.

## Solution Validation

Model Accuracy: The model was evaluated using validation accuracy and loss metrics. Training results are recorded in the notebook.

Manual Testing: Predictions were tested on sample images using both the UI and API interface.

Docker Verification: Successful Docker builds and container runs confirmed the reproducibility and correctness of the containerized app.

You can validate that the container is running correctly by visiting http://localhost:8501 for the Streamlit app.