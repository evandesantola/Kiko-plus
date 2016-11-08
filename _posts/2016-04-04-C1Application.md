---
layout: post
title: "Capital One Software Submit Application Project"
description: "A news summarization tool that also incorporates a bit of NLP"
date: 2016-05-22
tags: [Projects, Hackathons]
comments: true
share: true
---

# Foreward

This webapp was created for the Capital One software summit. I was under time constraints this month due to classes, homework, internship applications, research, other software challenges, and a video lecture series I have been asked to produce. As such, I could only spend around 5 hours producing this. To make a product quickly, I recycled some code I wrote at hackathons and use APIs for the web scraping and keyword extraction. Note that the code of this product is not representative of the typical quality work that I usually produce; I've had an extremely hectic month and have only been able to devote a few hours to its development.

# What it is:

NewsFlash is a text summarization web app that takes in either a URL or keywords relating to a news article and then summarizes the news the linked article. It provides the following:

1.Information and context about the author of the article (by searching for the author's biography and then providing a summarized version along with the article summary)

2.Relevant links to Wikipedia, based on important keywords in the article; users can click these link and go directly to the wikipedia page of the keyword to learn more

3.Provides related news articles, based on important keywords in the article (note that this is a bonus objective that I created). Users can either link directly to these sites, or copy and paste the article text into the search bar for a summarization of the articles.

4.Allows users to "crawl" thrugh related news articles by clicking on the news article links at the side. The article clicked is automatically summarized, author's wikipedia page located, keywords extracted, etc. New articles are then available on the sidebar for users to click again, repeating the process ad infinitum (a sort of Wikipedia game for the news).

#How it does it:

Newsflash is powered by flask, a python microframework (see views.py) and bootstrap. NewsFlash takes in a URL, and then uses Alchemy API to extract the body of the article, the author, keywords and article title. The text is then summarized with a common text summarization algorithm I implemented (see helperFunctions.py) during BostonHacks. I then used Bing API to gather relevant links to wikipedia about the extracted keywords of the article, as well as to locate a link to the author's wikipedia page (if it exists) and other related news articles. After the author's wikipedia page is located, it is summarized and placed below the summary of the article.

# Challenges I encountered:

I am primarily a backend programmer, with an interest in healthcare informatics, machine learning and computational game theory. As such, I do not have extensive experience in front end. Because I was under time constraints (see the foreword), I didn't have the time to complete a flashy front end design.
Another challenge I encountered was that I originally intended to use Alchemy API to grab related and recent news articles. However, I quickly found that these articles are not be the same articles that consumers might be interested. While the related articles provided by Alchemy API might be interesting if I was doing an NLP project (or some project that required large corpuses of related and time sensitive articles), many of them came from extremely obscure sources, and most contained information irrelavent to the original article (although they shared some common keywords). As such, I used Bing API to grab relevant news articles, wikipedia articles and information about the author. My final and greatest challenge was time. I am under extreme time constraints during this time of the year, as mentioned above in the forward. As such, I am unable to spend the time to create a nice, polished product as I normally would be able to do during a hackathon, where more time is available. If you wish, you can check out my first place winning submission for BostonHacks, my first place winning submission for HackIllinois (as well as Best Microsoft Hack and Best Use of Azure), and my Best Health Hack winning PennApps submission at my devpost, http://devpost.com/edesanto

# To Run:

This project uses virtualenv and Python 2.7. Set up virtualenv, install the dependencies in the requirements.txt file and then run the project on localhost:5555 by navigating to the directory with runserver.py and running the "python runserver.py" . You may have to install alchemy API manually, as you cannot pip install it. If so, just follow the directions on https://github.com/AlchemyAPI/alchemyapi_python

[Link to repo](https://github.com/evandesantola/CapitalOneMindSumo)