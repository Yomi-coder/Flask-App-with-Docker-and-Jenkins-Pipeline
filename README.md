# Flask App with Docker and Jenkins Pipeline

A beginner-friendly DevOps project showcasing a simple Flask application containerized with Docker and automated with Jenkins CI/CD pipeline.

## Project Overview

This project demonstrates:
- ✅ Flask web application
- ✅ Docker containerization
- ✅ Jenkins CI/CD pipeline
- ✅ Multi-stage deployment workflow

## Project Structure

```
├── app/
│   └── app.py              # Flask application
├── dockerfile              # Docker image configuration
├── Jenkinsfile            # Jenkins pipeline definition
├── requirements.txt       # Python dependencies
└── README.md             # This file
```

## Prerequisites

- **Python 3.8+** (for local development)
- **Docker** (for containerization)
- **Jenkins** (for CI/CD pipeline)
- **Git** (for version control)

## Installation & Running

### Option 1: Run Locally

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/Flask-App-with-Docker-and-Jenkins-Pipeline.git
cd Flask-App-with-Docker-and-Jenkins-Pipeline

# Create virtual environment
python -m venv venv
venv\Scripts\Activate.ps1

# Install dependencies
pip install -r requirements.txt

# Run the application
python app/app.py
```

Access the app at: `http://localhost:5000`

### Option 2: Run with Docker

```bash
# Build the Docker image
docker build -t flask-app:latest .

# Run the container
docker run -p 5000:5000 flask-app:latest
```

Access the app at: `http://localhost:5000`

### Option 3: Run with Jenkins Pipeline

1. Set up Jenkins server
2. Create a new Pipeline job
3. Point it to this repository and `Jenkinsfile`
4. Click "Build Now"

Jenkins will automatically:
- Clone the code
- Build Docker image
- Run the container on port 8081

## API Endpoints

| Endpoint | Method | Response |
|----------|--------|----------|
| `/` | GET | "Hello World" |

## Jenkins Pipeline Stages

1. **Checkout Code** - Clones repository from GitHub
2. **Check Docker** - Verifies Docker installation
3. **Build Docker Image** - Creates Docker image
4. **Stop Old Container** - Stops running container
5. **Run Container** - Starts new container on port 8081

## Technologies Used

- **Flask** - Python web framework
- **Docker** - Container platform
- **Jenkins** - CI/CD automation
- **Python 3.8** - Programming language

## File Descriptions

### `app/app.py`
Simple Flask application that returns "Hello World" on the root endpoint.

### `dockerfile`
Docker configuration that:
- Uses Python 3.8-slim base image
- Installs Flask dependency
- Runs the Flask application

### `Jenkinsfile`
Jenkins pipeline configuration with stages for:
- Code checkout from GitHub
- Docker version verification
- Docker image building
- Container management and execution

### `requirements.txt`
Python dependencies required for the project.

## Quick Commands

```bash
# Local development
python app/app.py

# Docker build
docker build -t flask-app .

# Docker run
docker run -p 5000:5000 flask-app

# Jenkins pipeline
# Set repository URL to this GitHub repo in Jenkins
```

## Author

DevOps Learning Project

## License

MIT License

## Support

For issues or questions, please create an issue in the GitHub repository.
