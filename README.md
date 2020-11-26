# Proposal

## What will (likely) be the title of your project?

Flowchart Fighters

## In just a sentence or two, summarize your project. (E.g., "A website that lets you buy and sell stocks.")

A python application which takes a user described fight pattern (a fighting flowchart) and allows an AI to perform that fight pattern in a selected traditional 2D fighting game.

## In a paragraph or more, detail your project. What will your software do? What features will it have? How will it be executed?

__Problem Statement__

![Flowchart Ken Image](https://i.kym-cdn.com/entries/icons/facebook/000/001/065/ken.jpg "Optional Title")

There’s a meme called “Flowchart Ken” (see above), describing a fighting game play style with the Street Fighter character Ken which revolves around one move - “Shoryuken”. This playstyle has been heavily criticized for how easy yet effective it is, and because of that it is a playstyle you will encounter a lot if you play Street Fighter at a tournament level, with some slight differences from player to player. Because tournaments usually do best of three games, by the time you finally figure out your opponent's flowchart, you have already lost.

When I first got into fighting games, I constantly lost to these “Flowchart Ken’s”, “Flowchart Ryu’s”, “Flowchart Foxes”, basically most fighting game players who were fighting by following a simple yet effective flowchart style of gameplay. Eventually, I got frustrated by the flowchart style of gameplay, and tried to figure out how to beat it.

The problem was there were very few ways to actually learn how to beat flowchart play styles which are not infuriating or expensive.
- Training modes in fighting games are often lacking in customization options so you cannot set up a flowchart dummy to practice against using training tools.
- Actual active fighting game computer opponents (often known as CPUs) do not use strategies you would actually see in tournaments. Rather, they mimic difficulty by reacting to your inputs faster than most humans can and by using special moves which are difficult to physically execute for a human being. It has its value yes, but it is not an actual strategy.
- Playing against someone with a flowchart style in person costs a tournament entry fee (and likely your health and safety given COVID-19)
- Fighting game experiences online are essentially unplayable if you do not live in the same region (and I live in Zimbabwe)

__Question__
*How can I, and other fighting game players in remote regions, get valuable practice against common tournament play styles without compromising our safety/subjecting ourselves to poor online experiences?*

__Solution__
My software is going to be a python desktop application which runs alongside the application file for a traditional 2D fighting game (Street Fighter). First, the application will be configured with an image classifier trained on sprites and sprite sheets from the game. Then it will take an outlined fighting flowchart as an input during configuration. Once fully configured with the flowchart data and sprite information on the game, the python application will extract the video frames continuously from the fighting game application window once the application starts running. It then analyzes those frames, and then using the trained image classifier, classifies which actions are occurring in the fighting game at that frame. From there, it consults the flowchart to see which action should be taken in response to the action on screen. Finally, it sends a keyboard input to the fighting game application window which corresponds to the action specified by the flowchart.

Overall, this should allow you to go into the Local Versus and practice against a flowchart style of gameplay without needing to play online or use the fighting game’s built in AI.

__Features__
- Flask website where:
    - Users can upload image datasets and formatted flowcharts.
    - A python microservice processes the dataset and trains an image network.
    - A python script processes the flowchart document into a configuration file.
    - Users can download a folder with the python desktop application, the exported image network, and the configuration file.
- Python Desktop Application which:
    - Extracts image frames from the fighting game application window
    - Classifies the action on screen using the trained image classifier
    - Searches the flowchart in the configuration file to find which action should be performed in response
    - Sends a keyboard input(s) to the application window

## If planning to combine CS50's final project with another course's final project, with which other course? And which aspect(s) of your proposed project would relate to CS50, and which aspect(s) would relate to the other course?

Not Applicable

## If planning to collaborate with 1 or 2 classmates for the final project, list their names, email addresses, and the names of their assigned TFs below.

Not Applicable

## In the world of software, most everything takes longer to implement than you expect. And so it's not uncommon to accomplish less in a fixed amount of time than you hope.

### In a sentence (or list of features), define a GOOD outcome for your final project. I.e., what WILL you accomplish no matter what?

A good outcome of my final project will be a python application which can execute at least 2 fighting flowcharts with one specific character (Ken) versus another specific character (Chun-Li) through image recognition of the game’s frames.

__Features__
- Python Desktop Application which:
    - Extracts image frames from the fighting game application window
    - Classifies the action on screen using the trained image classifier
    - Searches the flowchart in the configuration file to find which action should be performed in response
    - Sends a keyboard input(s) to the application window
- Use Cases
    - Should work on 2 fighting flowcharts
    - Should work on 2 characters in Street Fighter

### In a sentence (or list of features), define a BETTER outcome for your final project. I.e., what do you THINK you can accomplish before the final project's deadline?

A better outcome would be a python desktop application which can execute any number of fighting flowcharts for any character on the Street Fighter roster.

__Features__
- Python Desktop Application which:
    - Extracts image frames from the fighting game application window
    - Classifies the action on screen using the trained image classifier
    - Searches the flowchart in the configuration file to find which action should be performed in response
    - Sends a keyboard input(s) to the application window
- Error Handling/Reporting CLI
    - Report flowchart steps
    - Report errors when the characters specified in the flowchart aren’t there
    - Report data on the accuracy and confidence of the image classifier
- Use Cases
    - Should work on a variety of fighting flowcharts (testing 3)
    - Should work on any character in the Street Fighter roster (testing all)

### In a sentence (or list of features), define a BEST outcome for your final project. I.e., what do you HOPE to accomplish before the final project's deadline?

The absolute best outcome of my final project is a generic solution, where any user can upload a specially formatted dataset of any traditional 2D fighting game’s sprite data and a specially formatted document detailing the flowchart. After that, they should be able to download a python application with a custom configuration file and a custom trained image network which they can then run alongside a fighting game in order to execute/fight against their described fighting flowchart.

__Features__
- Flask website where:
    - Users can upload image datasets and formatted flowcharts.
    - A python microservice processes the dataset and trains an image network.
    - A python script processes the flowchart document into a configuration file
    - Users can download a folder with the python desktop application, the exported image network, and the configuration file.
- Python Desktop Application which:
    - Extracts image frames from the fighting game application window
    - Classifies the action on screen using the trained image classifier
    - Searches the flowchart in the configuration file to find which action should be performed in response
    - Sends a keyboard input(s) to the application window
- Error Handling/Reporting CLI
    - Report flowchart steps
    - Report errors when the characters specified in the flowchart aren’t there
    - Report data on the accuracy and confidence of the image classifier
- Use Cases
    - Should work on a variety of fighting flowcharts (testing 3)
    - Should work on any character in a fighting game roster (testing 5)
    - Should work on a variety of 2D fighting games (testing 3)

In summary, in the best-case training and configuration of the application should happen at the website level, the end user should be able to simply upload the image dataset (which in real-world cases needs to be curated by one person once), and the flowchart. Afterwards the end user just downloads the application and runs it.

## In a paragraph or more, outline your next steps. What new skills will you need to acquire? What topics will you need to research? If working with one of two classmates, who will do what?

__Research Topics__
- Computer Vision Frameworks (OpenCV, MATLAB, TensorFlow)
- Convolutional Neural Networks (For understanding purposes)
- Image Recognition Networks
- Image Classification
- Keyboard Hardware Inputs

__Skills I Will Need to Acquire__
- Python Desktop Application Programming
- Computer Vision Programming
- Create Image Based Datasets
- Hardware Input Simulation

__Next Immediate Steps__
The priority is to get a proof of concept up and running as quickly as possible. Since image recognition and response are the most complex parts of this project, the requirements of a POC would be:
1.	Train my own image classifier on a small image dataset
2.	Get video frames from any application window containing an image
3.	Classify the image from the application window using my classifier
4.	Print a unique response to the CLI based on the image classified.

From there, I can add the remaining features of the project around the POC. For example, I will eventually change the small image dataset to an image dataset formed from images of the actual game, the unique response based on the image classified will turn into a keyboard input, etc.
