---
layout: post
title: "WhatsUpDoc -- BostonHacks F15"
description: "Grandprize Winner of BostonHacks, Microsoft Imagine Cup National Semi-Finalist"
date: 2015-11-01
tags: [Hackathon]
comments: true
share: true
---

#Inspiration
The primary motivation for development of WhatsUpDoc was the existing problem faced by migrants and refugees who do not have access to smartphones and the internet. The refugees around the world are facing a health crisis which impacts not only them but also their families. We wanted to provide the refugees with a simple solution that would try to ameliorate their present condition. After, several sessions of intensive brainstorming over these problems, we realized the lack of access to heathcare information is the central most issue faced by the people in technologically backward areas. We plan to create a tool that would bring basic medical information to the people in need of immediate attention, who otherwise would not have access to the modern medical information.

#What it does
WhatsUpDoc looks after the modern day client-doctor challenges. Around the world there are a plethora of patients suffering from various ailments. WhatsUpDoc tries to provide an a quick remedy to them. A help in need is a help indeed !

WhatsUp Doc allows its users to call us (a telephonic call), and we try to solve their problems. The online call (“speech”) by users is converted to a “text” using the Microsoft Azure Speech recognition API. This text is then used to mine the internet for relevant keywords. Internet helps to offer a quick remedy. We present our users the most prevalent and effective choice. A key point to note here is that this whole process occurs while our users are on-the-call, and an effective tool to connect with users is Twilio.

The information that we target points to the most intelligent (preferred) link on the Bing. We use Bing API incorporated with WebMD database to search for the user query. We then used Machine Learning to find the most relevant diagnosis corresponding to the caller’s issue . This helps us to refine our search space. We take the most important diagnosis and search it on Mayoclinic.com which points us to possible treatments and remedies to the problem. We summarize the data from this webpage by an effective extraction technique which is then converted to speech and read aloud to the caller.

It should be noted that our technique works in real time. A real time application expects a quick response as one cannot expect user to stay on the call for huge amount of time. To facilitate this task we restrict our summarization results to 150 words, which can be easily outputted in a minute. We present these results back to the user as a speech. Hence, we also perform a text-too-speech recognition task. For this process we have used the Microsoft Speech recognition API.

#How I built it
After mapping out the program flow and different APIs we wanted to use, we began coding. First we used Twilio’s API to create a phone call that would convert the user's voice into speech (.wav) file. We used HP’s Haven-OnDemand Text Extractor and Bing API to extract document text from medical databases so that we could have a usable corpus to search for medical terms. Next, we refined our usage of Bing API and Twilio in order to create a functional product that could communicate and receive feedback from the user.

We encountered problems attempting to use HP’s Voice to Speech, and after a significant amount of time attempting to address the long processing times HP’s Voice to Speech, we decided to go with Microsoft’s Project Oxford to handle speech to text and text to speech. Next, we attempted to use HP’s Haven’s Training and Prediction APIs, but due to unforeseen problem’s with Haven’s inability to handle JSON files, and no documentation available that indicated this, we were unable to develop full functionality for this.

#Challenges I ran into
We encountered problems attempting to use HP’s Voice to Speech, and after a significant amount of time attempting to address the long processing times HP’s Voice to Speech, we decided to go with Microsoft’s Project Oxford to handle speech to text and text to speech. Next, we attempted to use HP’s Haven’s Training and Prediction APIs, but due to unforeseen problem’s with Haven’s inability to handle JSON files, and no documentation available that indicated this, we were unable to develop full functionality for this.

#Accomplishments that I'm proud of
WhatsUpDoc tries to solve the problems of the people who lack adequate resources. We believe on our motto that “a help in need is a help indeed”. Our application is successfully able to map a link between the user query and the instantaneous response. We provide a real time response to the user who calls up through his phone (on a specified number) and gets a quick response to his health issues. To perform this task we do a streamline call handling, speech recognition, speech-to-text conversion, effective multi-level query searching on the internet, efficient text summarization and text-to-speech recognition. All this task occurs while the user is online, on the call, that is real-time.

#What I learned
The first insight while developing such an API is the importance of real-time events. A real-time event requires faster response and highlights the immediate user needs. We also realized the tradeoff0 of the speech-to-text and vice versa communication media. As the size of data increases the performance of these API’s diminishes. We were able to create a simple yet effective summarization API that provides useful insights from the input text. We realized the easily overlooked but highly overwhelming code integration strategies. We believe creating separate modules is one task, but integrating it into a working system is another task, and even more challenging.

#What's next for WhatsUpDoc
We would like to extend our application to incorporate more effective user response. We plan to allow user to respond whether he/she is happy with the remedy suggested by us. A feedback approach will help us to provide client satisfaction. We also plan to perform data mining on the user problems. The mined results can provide an insight that shall help us to categorize the users on the basis of country, state and diseases. Another future scope is to email the users with a comprehensive solution to their problem. Such a mail can act as a guide for the user.