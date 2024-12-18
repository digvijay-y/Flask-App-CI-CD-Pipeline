# Python Flask App with Docker and GitLab CI/CD Pipeline

This project demonstrates containerization of a Python Flask application using Docker and automation of the build pipeline using GitLab CI/CD. The repository is designed to showcase CI/CD concepts, including dependency management and container image building.

---

## **Features**
- Containerization of a Python Flask app using Docker.
- Automated build pipeline using GitLab CI/CD.
- Organized multi-stage pipeline (Build and Test).
- Ensures code quality and efficient deployment workflows.

---

## **Technologies Used**
- **Docker**: For creating lightweight, portable containers.
- **GitLab CI/CD**: For pipeline automation.
- **Python (Flask)**: As the sample application framework.

---

## **Getting Started**

### **Prerequisites**
- Docker installed on your system.
- GitLab account (if you want to replicate the CI/CD pipeline).
- Basic understanding of Docker and CI/CD pipelines.

---

### **Steps to Run Locally**
1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>

2. Build the Docker image:

   ```bash
   docker build -t python-app 

3. Run the container:
   ```bash
   docker run -p 5000:5000 python-app

4. Access the application:

   Open your browser and navigate to http://localhost:5000.


## CI/CD Pipeline Workflow

The GitLab CI/CD pipeline automates the following stages:

    Build: Builds the Docker image for the Flask app.
    Test (Optional): Runs unit tests using Python's unittest module.

You can replicate this pipeline by including the .gitlab-ci.yml in your GitLab repository.

## **Pipeline Configuration (.gitlab-ci.yml):**
    ```yaml
    image: docker:latest
    
    services:
      - docker:dind
    
    variables:
      DOCKER_DRIVER: overlay2
    
    stages:
      - build
      - test
    
    build:
      stage: build
      script:
        - docker build -t python-app .
        - docker images
    
    test:
      stage: test
      script:
        - docker run --rm python-app python -m unittes

## **Project Structure**
    ```bash
    <repo-name>/
    ├── app.py                # Main Flask application
    ├── Dockerfile            # Docker image instructions
    ├── requirements.txt      # Python dependencies
    ├── .gitlab-ci.yml        # CI/CD pipeline configuration
    └── README.md             # Project documentation
