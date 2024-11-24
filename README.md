
# Credit Default Prediction Project

## Project Overview

This project uses credit client data to build a machine learning model that predicts whether a client will default on their payment in the next month. The workflow includes data preprocessing, exploratory data analysis (EDA), feature engineering, model training, and serving predictions using an XGBoost model.

## Project Structure

```plaintext
Credit Default Prediction Project/
│
├── data/                      # Contains the dataset
│   └── default of credit clients.xls
│
├── environment_project/       # Folder with your model, scripts, and dependencies
│   ├── Dockerfile             # Dockerfile for running the service
│   ├── train.py               # Script for training and saving the model
│   ├── predict.py             # Script for serving predictions
│   ├── xgb_model.pkl          # Trained XGBoost model
│   ├── dv.pkl                 # DictVectorizer model
│   └── requirements.txt       # List of Python dependencies
│
├── venv/                      # Virtual environment folder
│   ├── Scripts/               # Scripts for activating the environment
│   ├── lib/                   # Installed Python libraries
│   └── pyvenv.cfg             # Configuration for the virtual environment
│
├── data_dictionary.md         # Data dictionary
├── notebook.ipynb             # Jupyter notebook for EDA, model selection, and feature engineering
├── README.md                  # Project documentation
```

---

## Setup and Installation

### 1. Clone the Repository
Clone this repository to your local machine:
```bash
git clone https://github.com/your-repo-url.git
cd "Credit Default Prediction Project"
```

### 2. Set Up Virtual Environment
The project uses a Python virtual environment to manage dependencies.

#### Activate the virtual environment
On **Windows**:
```bash
venv\Scripts\activate
```
On **Linux/MacOS**:
```bash
source venv/bin/activate
```

#### Install dependencies
After activating the virtual environment, install the required dependencies:
```bash
pip install -r environment_project/requirements.txt
```

---

## Running the Project

### 1. Train the Model
Run the `train.py` script to train and save the model:
```bash
python environment_project/train.py
```

### 2. Serve Predictions
Use the `predict.py` script to serve predictions:
```bash
python environment_project/predict.py
```

---

## Docker Deployment

Build and run the Docker container for the service:
1. Navigate to the `environment_project/` folder.
2. Build the Docker image:
   ```bash
   docker build -t credit-default.
   ```
3. Run the container:
   ```bash
   docker run -d -p 9696:9696 --name Credit credit-default.
   ```
### Docker Build Success

Below are the screenshots demonstrating the successful Docker image builds for the project:

![Docker Build Success 1](https://github.com/KipyegonH/Credit_Default_Project/blob/main/images/successful%20builddocker%20images.1.jpg)

![Docker Build Success 2](https://github.com/KipyegonH/Credit_Default_Project/blob/main/images/successful%20build%20docker%20image2.jpg)

---

## Data Dictionary

Refer to `data_dictionary.md` for detailed information about the dataset fields and their descriptions.

---

## Notebook Analysis

`notebook.ipynb` contains:
- Exploratory Data Analysis (EDA)
- Feature engineering
- Model selection and tuning
- Insights and visualizations

## Deployment
This project can be deployed locally using Docker or to the cloud using AWS Elastic Beanstalk. Below are the detailed steps for both methods:

### Deploy Locally with Docker

#### Step 1: Install Docker
Ensure Docker is installed on your system. If not, refer to the [Docker installation guide](https://docs.docker.com/get-docker/).

#### Step 2: Build the Docker Image
Run the following command to create a Docker image for the project:
```bash
docker build -t credit-default .
```

#### Step 3: Run the Docker Container
Start the Docker container and expose it on port `9696`:
```bash
docker run -d -p 9696:9696 --name Credit credit-default.
```
#### Step 4: Access the Service
```
The service will be available at [http://localhost:9696](http://localhost:9696).
```

### Deploy to AWS Elastic Beanstalk

#### Step 1: Install AWS Elastic Beanstalk CLI
Install the Elastic Beanstalk CLI by following the [AWS EB CLI installation guide](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html).

#### Step 2: Initialize Elastic Beanstalk
In the project directory, run:
```bash
eb init
```
- Choose your AWS region.
- Enter an application name (e.g., `credit-default`).
- Select `Docker` as the platform.
- Set up SSH access if required for troubleshooting.

#### Step 3: Create an Elastic Beanstalk Environment
Create a new environment to host the application:
```bash
eb create credit-card-default-env
```

#### Step 4: Deploy the Application
Use the following command to deploy the project to Elastic Beanstalk:
```bash
eb deploy
```

#### Step 5: Access the Application
Once deployed, Elastic Beanstalk will provide a URL to access your application. You can also use:
```bash
eb open
```

#### Step 6: Monitor and Manage
- To view logs:
  ```bash
  eb logs
  ```
- To terminate the environment when no longer needed:
  ```bash
  eb terminate credit-default-env
  ```

## Contributing
Contributions are welcome! Feel free to submit a pull request or report issues.

