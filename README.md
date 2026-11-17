# Machine Learning Deployment for Logistics

This project demonstrates the development and deployment of a Machine Learning model for the logistics area.

The application predicts the type of product based on package weight and packaging type. It includes both the model training script and a Flask web application that allows users to submit product information and receive a prediction through a simple web interface.

## Project Objective

The main objective of this project is to show how a Machine Learning model can be trained and deployed in a web application for logistics-related classification tasks.

The application allows users to:

* Train a Machine Learning classification model;
* Encode categorical variables using label encoders;
* Save the trained model and preprocessing transformers;
* Load the saved model in a Flask application;
* Submit product information through a web form;
* Predict the likely product type based on package characteristics.

## Technologies Used

* Python
* Flask
* Pandas
* Scikit-learn
* Joblib
* HTML

## Project Structure

```text
.
├── p1_modelo.py                              # Script used to train and save the model
├── p1_deploy.py                              # Flask application for model deployment
├── template.html                             # HTML form used by the web application
├── versoes.py                                # Script to check Python and package versions
├── requirements.txt                          # Project dependencies
├── LEIAME.txt                                # Original execution instructions
├── modelos/
│   ├── modelo_logistica.pkl                  # Trained Machine Learning model
│   ├── transformador_tipo_embalagem.pkl      # Encoder for packaging type
│   └── transformador_tipo_produto.pkl        # Encoder for product type
└── README.md                                 # Project documentation
```

## How the Project Works

The project has two main steps:

1. **Model training**

   * A small logistics dataset is created with package weight, packaging type, and product type.
   * The categorical variables are encoded using `LabelEncoder`.
   * A Decision Tree classifier is trained to classify the product type.
   * The trained model and encoders are saved to disk using Joblib.

2. **Model deployment**

   * The Flask application loads the trained model and encoders.
   * The user enters the package weight and packaging type in a web form.
   * The packaging type is transformed using the saved encoder.
   * The model predicts the product type.
   * The predicted product type is displayed on the web page.

## Input Features

The model uses the following input variables:

* Package weight in grams
* Packaging type

The available packaging types are:

* Cardboard Box
* Bubble Wrap

## Output

The model predicts the likely product type, such as:

* Smartphone
* Tablet

## Installation

Create a Conda virtual environment:

```bash
conda create --name logistica python=3.13
```

Activate the environment:

```bash
conda activate logistica
```

Install `pip` and the project dependencies:

```bash
conda install pip
pip install -r requirements.txt
```

## Training the Model

To train the model and save the required files, run:

```bash
python p1_modelo.py
```

This script trains the classifier and saves:

```text
modelos/modelo_logistica.pkl
modelos/transformador_tipo_embalagem.pkl
modelos/transformador_tipo_produto.pkl
```

## Running the Web Application

After training the model, start the Flask application with:

```bash
python p1_deploy.py
```

Then access the application in the browser using the local address provided by Flask.

## Web Interface

The web page allows the user to enter:

* Package weight;
* Packaging type.

After submitting the form, the application displays the predicted product type.

## Checking Package Versions

To check the Python and package versions used in the project, run:

```bash
python versoes.py
```

## Notes

* The model must be trained before running the Flask application.
* The saved model and encoders must be available inside the `modelos` folder.
* The application expects the same input structure used during model training.
* This project was developed for educational purposes and demonstrates a simple Machine Learning deployment workflow.

## Author

Project developed as a practical study on Machine Learning model deployment for logistics.
