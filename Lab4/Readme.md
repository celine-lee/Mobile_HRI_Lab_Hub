# Make the robot see
**List the names and NetID for your partners here.**

Build off of Lab 3 from last week. This week's material can be done rather quickly.


## Prep

### For this lab, you will need:
1. Your laptop
2. Pi Camera

### Before you come to the lab on Thursday, please do the following:
1. Install VNC viewer from [here](https://www.realvnc.com/en/connect/download/viewer/) if you haven't. 

### Deliverables for this lab are: 

0. A screenshot of the working VNC viewer with a working image view.

1. Answers to the reflection questions in Part D. 

### The Report 
This README.md page in your own repository should be edited to include the work you have done (the deliverables mentioned above). Following the format below, you can delete everything but the headers and the sections between the **stars**. Write the answers to the questions under the starred sentences. Include any material that explains what you did in this lab hub folder, and link it in your README.md for the lab.

## Lab Overview
For this assignment, you are going to:

A) [Connect your camera](#-a-connect-your-camera)

B) [Connect to your Pi (VNC Viewer)](#part-b-connect-to-your-pi-through-vnc-viewer)

C) [People Detection](#part-c-people-detection)

Labs are due on Tuesdays before class. Make sure this page is linked to on your main class hub page.

## Part A. Connect your camera
Plug in the Pi camera to your RPi.

## Part B. Connect to your Pi through VNC Viewer
Start VNC Viewer, if prompted to sign in, "select Use VNC without signing in" in the bottom.

In the text box "Enter a VNC Server address or search", type in `Your_RPi_IP:1` (e.g. `10.56.131.31:1`).
> When prompted "server not encrypted", click "continue"
<img src="Images/vnc_warning.jpg" width="300">

**Password**: `student`

You should now log in to your Pi through VNC Viewer.

> <img src="Images/vnc.jpg" width="300">

Open a terminal, install `libcamera-dev`.

```bash
sudo apt install libcamera-dev
```
> <img src="Images/terminal.jpg" width="300">

## Part C. People Detection
First, let's test if your camera is working properly. 
```bash
# In a terminal in VNC Viewer
cd
curl -LJO https://raw.githubusercontent.com/FAR-Lab/Mobile_HRI_Lab_Hub/main/Lab4/test_camera.py
python3 test_camera.py
```
**Please include a screenshot of the working VNC viewer with a working image view.**

This exercise is based on this [The Data Frog Tutorial](https://thedatafrog.com/en/articles/human-detection-video/#:~:text=People%20detection,work%20well%20in%20other%20cases.) online. Your CPU will get toasty, so put on a **heat sink**. 

```
# In a terminal in VNC Viewer
curl -LJO https://raw.githubusercontent.com/FAR-Lab/Mobile_HRI_Lab_Hub/main/Lab4/people_detection.py
python3 people_detection.py
```

Optional: Another example you can try is from [PyTorch](https://pytorch.org/tutorials/intermediate/realtime_rpi.html) (installed already on your system). You will need to write a few lines of code to load the labels yourself. 

## Part D. Reflection

Reflect on the following questions:

1. For your favorite prototyped interaction that you have thought of so far, reflect upon how a camera connected to your Pi could be useful.

A camera connected to the Pi would be super useful in practically all of the prototyped interactions we have designed. Because the interactions rely on existing around people and reacting to them, being able to recognize a human (and perhaps the actions / facial expressions of that human) would be critical. In the WoZ setups so far, we have somebody behind the scenes doing all of the human recognition and interaction for the robot. If we want to automate any of it, e.g. we want the mummy robot to automatically turn on its light and start moving quickly as soon as it realized it is recognized and faced, we need a camera.

2. What issues do you foresee with this setup?

One challenge I foresee with the camera on the Pi is that the camera can only see a limited range in front of it. The robot is capable of moving in practically all planar directions, but it has no ability to see to its side or behind it unless it moves its entire body. This could definitely result in some bumping into of things, and especially given the low height of the robot, this could cause the robot to bump into things that cause irreversible damage to the robot.

3. How is the temperature? How is the speed? How is the connection?

When the camera was on, the Pi got really hot. We did have the heat sink, but I imagine that with extended use, this may not be enough and the heat could cause damage to humans that interact with it as well as the robot itself. The speed and connection were somewhat slow, but not of great concern for our applications thus far.

4. How is the view? Would it capture what you might need to see for your prototyped interaction (in question 1)?

The quality of the images coming in from the camera were somewhat low. Additionally, the view that the camera could see were practically ground-level. This means that if it is interacting with people, as it does in our scenarios, it will only see the feet if the robot is on the floor. We care to see the humans feet, as well as their facial reactions in many situations, so some sort of motorized control for the angle of the camera is important to capture our interactions. The mummy robot, for example, will not be totally able to tell if a human has noticed it and is looking at it, if it can only see the feet of the human. It might otherwise rely on being desk-level with a sitting human, but the situation in which the robot would be able to get itself on the table seems unlikely to arise.


Labs are due on Tuesdays before class. Make sure this page is linked to on your main class hub page.

### Again, deliverables for this lab are: 

0. A screenshot of the working VNC viewer with a working image view.


![VNC viewer](https://github.com/celine-lee/Mobile_HRI_Lab_Hub/blob/main/Lab4/terminal.pdf)


https://drive.google.com/file/d/12KFVBl2ftmmGbc3X2XeCN4nbwWLM7ggA/view?usp=sharing

1. Answers to the reflection questions in part D. 

