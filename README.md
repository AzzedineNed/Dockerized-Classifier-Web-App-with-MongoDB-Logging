# Dockerized-Classifier-Web-App-with-MongoDB-Logging

This project extends the functionality of the [Dockerized Classifier Web App 2](https://github.com/AzzedineNed/Dockerized-Classifier-Web-App-2) by adding a MongoDB service to log predictions. The web app classifies uploaded images of cats or dogs using a pre-trained ResNet50 model and stores the classification results in a MongoDB database.

## Features

- **Image Upload via Frontend**: Users can upload an image through the frontend web interface.
- **Image Classification in Backend**: The backend service processes the uploaded image using the pre-trained ResNet50 model and returns a classification (cat or dog).
- **MongoDB Logging**: Classification results, including the image name, predicted label, and confidence, are logged into a MongoDB database for storage and future analysis.
- **Dockerized Multi-Service Application**: The app includes three services (frontend, backend, and MongoDB) using Docker Compose, ensuring easy deployment and scalability.

## Requirements

- **Docker**: Ensure Docker is installed on your system.
- **Docker Compose**: To orchestrate the frontend, backend, and MongoDB services.

## How to Run the Project

### Step 1: Clone the repository

```bash
git clone https://github.com/AzzedineNed/Dockerized-Classifier-Web-App-with-MongoDB-Logging
```

### CD to the repo

```bash
cd Dockerized-Classifier-Web-App-with-MongoDB-Logging
```

### Step 2: Build and Run using Docker Compose

```bash
docker-compose up --build
```

This command builds all services (frontend, backend, and MongoDB) and starts them. Docker Compose automatically creates a shared network for seamless communication between services.

### Step 3: Access the Application

- **Frontend**: Open your web browser and go to http://localhost:5000 to access the upload interface.
- **MongoDB**: Data is stored in the predictions_db database within a collection called predictions. Use any MongoDB client to query the database using the connection string mongodb://localhost:27017 (as defined in docker-compose.yml).

### Step 4: Stop the Services

To stop the running services, use the following command:

```bash
docker-compose down
```

### How the System Works

- **Frontend (Flask)**: Users interact with the frontend by uploading an image through the web interface.
- **Backend (Flask)**: The frontend sends the uploaded image to the backend, where it is classified using the ResNet50 model.
- **Prediction and Result Display**: The backend returns the classification result to the frontend, which displays the prediction along with the confidence score.
- **MongoDB Logging**: The backend logs the classification result into MongoDB with details like image name, predicted label, and confidence score

### Networking

Docker Compose automatically sets up an internal network to facilitate communication between the frontend, backend, and MongoDB services. The services are isolated yet interconnected, ensuring secure and seamless communication.
