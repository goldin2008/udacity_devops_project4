[![vdurakci](https://circleci.com/gh/vdurakci/udacity_devops_project4.svg?style=svg)](https://circleci.com/gh/vdurakci/udacity_devops_project4)

## Project Summary

The goal of this project is to demonstrate the knowledge and skills to operationalize a Machine Learning Microservice as a Docker container. Once the container is validated as a standalone locally, it is uploaded to Docker Hub and deployed to a local Kubernetes cluster from there. Finally all source code is uploaded to GitHub and pushed to a CircleCI pipeline that validates the structure of Dockerfile and application Python code.

## How to Run Python Scripts and Web App?

The recommended way to run Python scripts during local testing is in a virtual Python environment. 

* Create a new virtual environment under `~/.devops` folder: `python3 -m venv ~/.devops`
* Activate the virtual environment you just created: `source ~/.devops/bin/activate`
* Now you can start the Python application with `python app.py`

## List of Files in the Repository

`README.md`: Readme file for the GitHub repository
`Dockerfile`: Dockre configuration file for creating the docker image
`Makefile`: Make file that includes the command to install the python dependencies (`make install`) and linting (`make lint`)
`app.py`: Main Python file for the flask application
`requirements.txt`: list of the dependency libraries required by the app
`run_docker.sh`: shell script to build, list and run the docker container
`upload_docker.sh`: shell script to tag and upload the docker image to Docker Hub
`run_kubernetes.sh`: shell script to run the container in a Kubernetes pod, list the pod and forward its port to the host port
`make_prediction.sh`: Shell script to call the application endpoint with test data
`model_data`: Folder where the trained model is stored
`output_txt_files`: Folder where the outputs of the run_docker.sh and run_kubernetes.sh scripts are stored

---

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

## Setup the Environment

* Create a virtualenv and activate it
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl
