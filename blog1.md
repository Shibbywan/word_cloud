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

I searched through the issues on the repository and found [this](https://github.com/amueller/word_cloud/issues/125). I read through it and discovered iPython, which is an interactive python shell. I installed iPython, and attempted to import wordcloud in it as seen in the following picture:

![](http://i.imgur.com/69KXHRw.png)

I learned that I was having the exact same problem as the user in the previous issue. pip seemed to not actually build word cloud correctly, and I was importing from the downloaded directory. I changed directory and was able to import the library using ipython.

## Artifact 2: Example + Console output

I ran the program using the example that was included in the repository. The example used the US constitution and created a word cloud from it. I got the following output:

![](http://i.imgur.com/hWtNq4u.png)

I wanted to run the program on something different so I copied the first few paragraphs of Patrick McKenzie's [Don't Call Yourself a Programmer](http://www.kalzumeus.com/2011/10/28/dont-call-yourself-a-programmer/) into a text file and ran the program on it. I got the following output:

![](http://i.imgur.com/iuHrs2G.png)

## Notes

The bug with Pillow seems to be quite big and I didn't see any mention of it in the install instructions, it may be a good question to ask later. Also, I learned that there is an issue with PIL (Python Imaging Library) and Pillow. Pillow is the successor of PIL and they actually interfere with each other if they are both installed. I feel like in my earlier attempts to install the software, I may have been hindered by this. 


