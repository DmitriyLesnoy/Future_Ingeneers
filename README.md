# Future_Ingeneers
progect to WRO 2021
Comand LIME, Vladivostok, category Future Ingineers

In the development of the LIME team project for the WRO competition in
the Future Engineers category was attended by Lineisky Akim -
programmer, designer, Ivan Terekhov - engineer,
electronics engineer, Glamozdin Yuri - our mentor and trainer.
                                                                                                                                                                                                                                                                                                                                     
The robot was programmed in Python version 3.9.3. The interpreter was PyCharm.
                                                                                                                
To connect the robot and the computer, the robot creates a wi-fi access point to which the computer is connected. Next, using the StartRobot application and the cv2 library, we load the program file onto the Raspberry microcomputer. He saves it to the SD card and then executes the code.
                                                                                                                                                 
As the code is executed, the Raspberry microcomputer continuously sends data packets to PyBoard with its unique number. The PyBoard microcontroller checks that the packet matches this number, in case of a packet malfunction, rejects it. Then the microcontroller already sends commands to the motor and servo

in the main program of our project, we use the cv2 libraries, regulators, RobotAPI and others.

Initially, we get an image from a 640x480 camera. Then we go straight until we find an image in a special HSV mask of blue or orange color no less than a certain number of pixels. It depends on what color we see first, we will understand in which direction we have to move in the future. After we have determined the direction of movement, we turn in the appropriate direction. If the blue line is the first, the direction of movement is counterclockwise, we turn to the left, if the orange line is the first, from the direction of movement is clockwise, we turn to the left.
                                                                                                                                                                                                   
If we need to pass a qualifying race or run a program without taking into account the signs, we have a special variable - a flag denoting qualifications.                                                                                                                                                                                                         
If it is set equal to True, the program will turn off the part responsible for reactions to road signs and will not react to them, it will just eat in a circle in the right direction.                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                                                     
Otherwise, if this qualification flag is equal to False, the robot will not change anything or disable any part of the program. He will go to the turn line, determine its color, and accordingly determine the direction of further movement, and will go 3 circles, bypassing the red signs on the right, and the green signs on the left.
                                                                                                                                                                                                                                                                                                                                       
Our algorithm for the movement of a robot with signs is built from several stages (stages).
These are: Movement to the line
         Turning stage - left or right
         Independent movement
         Finish
The first stage - movement to the line has already been mentioned above. The robot drives straight until it sees a blue or orange line. It depends on which line he sees first, he will understand in which direction he will need to move in the future.

The second stage - Independent movement is divided into 2 sub-parts: the movement regulator and the block of the regulator of rotation and steering of signs.

In the motion controller, the robot cuts out a part of the image received by the camera and according to a special HSV mask from the left or right edge, depending on the direction. In this way, we get a piece of the black line - the side along which we will go.
We define its y coordinates and outline height. Putting them together, we get a certain numerical distance of the robot from the edge - the side.
In the second part - Taxiing signs. We use HSV to find green and red signs, and then the closest to us - a larger contour. Then, knowing the direction and the color of the nearest sign, we decide in which direction we need to wrap. We add this cislo to the general error of the regulator, as a result of which the robot turns in the right direction.

The Finish, Hand Control and HSV tuning stages are pretty simple.

Finish - the robot travels a certain distance in time after passing 12 turns - 3 laps.

Manual control - when you press the arrows on the computer keyboard, the robot moves in the appropriate direction or turns the servo - steering wheels.

Setting up HSV. Here we can switch and watch masks of different colors. Also, here you can configure all the components and after setting or checking, save them and into a file from which values ​​for the filter will be taken in the future.

To load a specific program into the robot, we use a special program called "Start the Robot". When it starts, a special window opens with an interface for transferring files, launching the program and transferring video from the robot.
   There are several buttons in the window:
             "Start download" - downloads a specific program to the robot.
             "Start" - launches the program loaded on the robot.
             "Raw" - runs the verification program
             "Video" - launches video received in real time from the robot's camera
             "Connect to robot" - opens a menu of available robots to connect

We use the Wifi network to communicate with the robot.

System requirements for working with the Future Engineers project:

1. The operating system of the computer you will be working on is Windows 10
2. Program interpreter of the python language - PyCharm.
3. Programming language - Python 3.9.
4. The presence of a browser
5. Access to the repository on Github
Installing the required components:
1) Installing PyCharm
a) Go to PyCharm's official website official website
 
b) Next, select the Windows operating system.
c) Click the download button.
d) Next, the installation file will be downloaded
 
e) After installing it open it and run the file
f) Next, select the parameters you need.
2) Installing python language version 3.9
a) Go to python official site
b) Click on the Download button
c) Scroll down, you will see a list of versions that can be downloaded, select python 3.9
d) You will see the page of this version, scroll down and select the version for the 64-bit operating system
e) Next is the installation of the language file.
f) When it is installed, run it, select the options you want and download the language.
g) Then go to pychram, in the upper left corner there will be a File button
h) Then click on the Settings button
i) Then go to this section and select the language that you installed G
3) Installing the project folder from the Github repository:
a) You need to go to the link to the Github repository
b) Then click on the green Code button, then download the zip archive
c) The download of the project archive should start
d) Then unzip the file to a regular folder
Starting the robot:
a) Insert the 4.2 Volt batteries into the battery compartment of the robot. Do not confuse + and - batteries to avoid consequences.
a) Press the red power button on the robot.
b) When you turn on the PyBoard microcontroller, a sound with an increase in tone will sound, wait until the Raspberry Pi microcomputer starts up, after it finishes starting it will play a melody - a double trill.
Uploading the project to the robot:
a) Open PyCharm, click on the File button in the upper left corner.
b) Then click on the Open button
c) Next, by clicking on the folder icons in the window that opens, select the folder in which the unzipped GitHub repository of the Future Engineers project is located.
 
d) By default, the folder should be in this path, you can copy and paste into the search box C: \ Users \ user \ Downloads \ Future-Ingeneers
 
e) You should open the project folder
f) To upload files to the Raspberry Pi, you need to open the Windows network menu in the bottom right corner
 
g) Select Lime network
 
h) Then enter the password and connect to the network
 
i) Now go back to the PyCharm program, in the project files menu, select and open the Start Robot program
 
j) In the right-hand buttons at the top of the screen, click the Run button

k) Select the Run button, in the small window that opens, select the Start robot program
 
l) This window will open
m) To load the program on the robot, click on the Load Start button and select the program to start
 
n) To start starting the program on the robot, press the Start button
o) To stop the program on the robot, press the Stop button
p) To restart the program on the robot, click on the Raw button
q) To enable video broadcast from the robot, click the Video button
r) But before using all these buttons, you need to connect to the robot using the Connect to robot button.
 
s) Clicking on the button will open a list of robots available to you, select the first option
  
t) When the robot and computer are connected to each other, there will be an inscription:
Ways to connect to individual components:
a) To connect directly to the Raspberry Pi, you need to remove the Micro SD, then connect it to the computer, or use a USB cable, micro USB to plug it into the microcomputer and then into the computer.
b) To connect directly to PyBoard, you need to connect the Micro USB cable to the microcontroller connector and to the computer. 
