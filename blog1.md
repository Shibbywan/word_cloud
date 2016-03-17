# Assignment 1 
Kevin Saforo

## Overview

The open source project I chose is called **Word Cloud** which is a python program which generates a visual representation of words based on frequency. The creator's name is Andy, he has a blog which he titles "Andy's Computer Vision and Machine Learning Blog". 

The link can be found [here](peekaboo-vision.blogspot.ca).

In Andy's readme, he mentions that this software is used by a bot on reddit, to generate word clouds of submission histories and comments on request from any user. For similar purposes, the word cloud software is also used by a Twitter bot to generate word clouds of tweets for users. Finally, the word cloud software is also used by a program for Twitch.tv called "Chatstats". I chose this software because the idea is quite simple and the pictures it generates are quite visually pleasing.

## Artifact 1: Installation

I had quite a bit of trouble getting the software to work. I followed the readme, and initially i tried the following line of code:

    pip install wordcloud

I had to sudo this command, and the output seemed like it worked fine. However, in both python2 and python3, I couldn't manage to import the library.

![](http://i.imgur.com/AZgxO7B.png)

Instead, I decided to manually install the libraries using the instructions from the readme. The following lines of codes are given:

    wget https://github.com/amueller/word_cloud/archive/master.zip
    unzip master.zip
    rm master.zip
    cd word_cloud-master

Then, installing the requirements and package involves the following 2 lines:

    sudo pip install -r requirements.txt
    python setup.py install
    
![](http://i.imgur.com/NZof6Fo.png)

The installation fails, mentioning that 'jpeg' is required. I eventually learned that this was a bug with **Pillow**, an imaging library for python. I did some stack overflow searching and I found [this](http://stackoverflow.com/questions/34631806/fail-during-installation-of-pillow-python-module-in-linux). As provided in the post I used the following command:

    sudo apt-get install libtiff5-dev libjpeg8-dev zlib1g-dev libfreetype6-dev liblcms2-dev libwebp-dev tcl8.6-dev tk8.6-dev python-tk

I then ran the first command again:
    
    sudo pip install -r requirements.txt
  
Which worked, and gave me this:

![](http://i.imgur.com/PJSrXvZ.png)

Then I sudo-ran the next command and it worked. Although I still could not import any of the libraries in python2 or python3. I tried running the given example program directly from the downloaded directory. This was the result:

![](http://i.imgur.com/DshauvC.png)

I searched through the issues on the repository and found [this](
