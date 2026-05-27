#This is the logic API! That sends data to the website to show more memes

from flask import Flask, render_template
import requests
import json

app = Flask(__name__)

def get_meme():
    #Uncomment
    # sr = "/wholesomememes"
    # url = "https://meme-api.com/gimme" + sr
    url = "https://meme-api.com/gimme"
    response = json.loads(requests.request("GET", url).text)
    meme_large = response["preview"][-2]
    subreddit = response["subreddit"]
    return meme_large, subreddit

@app.route("/")
def index():
    meme_pic,subreddit = get_meme()
    return render_template("meme_index.html", meme_pic=meme_pic, subreddit=subreddit)

app.run(host="0.0.0.0", port=80)

---------------------------------------------------------------------------------------------
Here is the HTML of the website that I broke down
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Meme website</title>

  <style>
body {
    background-color: #000000;
    background-repeat: no-repeat;
    background-position: top left;
}

h1 {
    text-align: center;
    font-family: Arial, sans-serif;
    color: #ffffff;
    background-color: #000000;
}

p {
    text-align: center;
    font-family: Georgia, serif;
    font-size: 48px;
    font-style: normal;

* I had orginally tried to do this on vscode but I challenged myself to run my own server on Linode and us Flask to build a meme website which was fun along the process *



