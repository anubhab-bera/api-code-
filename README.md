# api-code-
from flask import Flask,jsonify

app = Flask(__name__)


from pandas import pandas as pd
from github import Github
import requests


info_url = 'https://api.github.com/repos/bzbarsky/rust-mozjs/contributors'

user_info = requests.get(info_url).json()
print (user_info)
print("*******************************")

@app.route('/contributors', methods=['GET'])
def omni():
    return jsonify({'contributors':info_url})

if __name__ == "_main_":
    app.run(debug=True)
