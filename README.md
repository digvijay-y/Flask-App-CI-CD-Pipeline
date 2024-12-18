# Python Flask App with Docker and GitLab CI/CD Pipeline

This project demonstrates containerization of a Python Flask application using Docker and automation of the build pipeline using GitLab CI/CD.

---

## **Features**
- Containerization of a Python Flask app using Docker.
- Automated build pipeline using GitLab CI/CD.
- Organized multi-stage pipeline (Build and Test).


---

## **Technologies Used**
- **Docker**: For creating lightweight, portable containers.
- **GitLab CI/CD**: For pipeline automation.
- **Python (Flask)**: As the sample application framework.

---

## **Getting Started**

### **Prerequisites**
- Docker installed on your system.
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
    Test (Optional): Runs unit tests(NIL for Now)

## **Project Structure**
    ```bash
    <repo-name>/
    ├── app.py                # Main Flask application
    ├── Dockerfile            # Docker image instructions
    ├── requirements.txt      # Python dependencies
    ├── .gitlab-ci.yml        # CI/CD pipeline configuration
    └── README.md             # Project documentation
