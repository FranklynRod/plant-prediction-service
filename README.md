
# plant-prediction-service

plant-prediction-service is Flask RESTful API that retrieves predictions from a TensorFlow model built with [Lobe](lobe.ai). It is utilized by [houseplant-app](https://github.com/Sarajvega/houseplant-app).

[Deployed Version](https://plant-prediction-service.azurewebsites.net/)

## How it works
A base64 image is sent with a `POST` request to the app, which returns an array of predictions and confidences. The server code that defines endpoints is in `app.py`. 

## Technologies
- Flask

## Usage

Clone or download the project on your computer to get started. You'll need Python 3.6 or 3.7 to run this starter project as well.

#### Windows

3. Create and activate a virtual environment  
```python
python -m venv .venv
.venv\Scripts\activate
```

4. Install dependencies  
```python
python -m pip install --upgrade pip && pip install -r requirements.txt
```

5. Run the server locally  
```python
python app.py
```

#### macOS

3. Create and activate a virtual environment
```python
python -m venv .venv
source .venv/bin/activate
```

4. Install dependencies
```python
python -m pip install --upgrade pip && pip install -r requirements.txt
```

5. Run the server
```python
python app.py
# or
export FLASK_APP=app.py
flask run
```

### Sending a request

1. Perform a post request to the target `http://localhost:5000/predict` with your base64 image. 
   
```JSON
{
  "image": "<base64 image>"
}
```

2. Successful requests return JSON with the confidences of your predictions.
```JSON
{
  "predictions": [
    {
      "predicted_label": 0.9105
    },
    {
      "another_label": 0.0895
    }
  ]
}
```

## Contributing
For changes, please open an issue first to discuss what you would like to change.

## Credits
Lobe's [flask-server](https://github.com/lobe/flask-server) starter project.

