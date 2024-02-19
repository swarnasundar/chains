import json
from pytz import timezone 
import pandas as pd
import numpy as np
import time
from datetime import datetime,timedelta,date
import pygsheets
from lxml import etree as et
import calendar
import pyrebase

def datafetch():
    try:
        firebaseConfig = {
            "apiKey": "your_api_key",
            "authDomain": "your_auth_domain",
            "databaseURL": "your_database_url",
            "projectId": "your_project_id",
            "storageBucket": "your_storage_bucket",
            "messagingSenderId": "your_messaging_sender_id",
            "appId": "your_app_id",
            "measurementId": "your_measurement_id"
        }
        
        firebase = pyrebase.initialize_app(firebaseConfig)
        db = firebase.database()
        
        path = r'C:\Users\SMAA\creds.json'
        gc = pygsheets.authorize(service_account_file='creds.json')
        sh = gc.open('HEADER')
        
        wk1 = sh[1]
        nft = wk1.get_as_df(start='A1', end='B23')
        
        nfttrend = nft.iloc[0, 1]
        nftspot = nft.iloc[1, 1]
        nftmaxpain = nft.iloc[2, 1]
        nftnetchange = nft.iloc[3, 1]
        nftdemand = nft.iloc[4, 1]
        nftsupply = nft.iloc[5, 1]
        nftceprem = nft.iloc[6, 1]
        nftpeprem = nft.iloc[7, 1]
        nftintratrend = nft.iloc[8, 1]
        nftcebuypoints = nft.iloc[9, 1]
        nftpebuypoints = nft.iloc[10, 1]
        bnfttrend = nft.iloc[11, 1]
        bnftspot = nft.iloc[12, 1]
        bnftmaxpain = nft.iloc[13, 1]
        bnftnetchange = nft.iloc[14, 1]
        bnftdemand = nft.iloc[15, 1]
        bnftsupply = nft.iloc[16, 1]
        bnftceprem = nft.iloc[17, 1]
        bnftpeprem = nft.iloc[18, 1]
        bnftintratrend = nft.iloc[19, 1]
        bnftcebuypoints = nft.iloc[20, 1]
        bnftpebuypoints = nft.iloc[21, 1]

        nifty = {
            "niftyspot": nftspot,
            "niftytrend": nfttrend,
            "niftynetchange": nftnetchange,
            "niftymaxpain": nftmaxpain,
            "niftydemand": nftdemand,
            "niftysupply": nftsupply,
            "niftyceprem": nftceprem,
            "niftypeprem": nftpeprem,
            "nftintratrend": nftintratrend,
            "nftcebuypoints": nftcebuypoints,
            "nftpebuypoints": nftpebuypoints,
            "bniftyspot": bnftspot,
            "bniftytrend": bnfttrend,
            "bniftynetchange": bnftnetchange,
            "bniftymaxpain": bnftmaxpain,
            "bniftydemand": bnftdemand,
            "bniftysupply": bnftsupply,
            "bniftyceprem": bnftceprem,
            "bniftypeprem": bnftpeprem,
            "bnftintratrend": bnftintratrend,
            "bnftcebuypoints": bnftcebuypoints,
            "bnftpebuypoints": bnftpebuypoints
        }
        
        db.update(nifty)
        print(nifty)
        
    except Exception as e:
        print("An error occurred:", e)

while True:
    datafetch()
    time.sleep(5)
