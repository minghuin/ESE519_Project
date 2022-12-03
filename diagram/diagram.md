
# Design
A intelligence clock system is designed with the screen of Pico4ml to show time and temperature information. The time should be initialized every time when it's connected to power as Pico4ml does not have its internal clock. 

# Feature
The basic feature is that the alarm will ring on the setting time. 

Besides, the temperature information is collceted by the temperature sensor of Pico4ml itself. 

Another interesting feature is that the brightness of the screen would automatically adjust based on the current environment, so your eyes wouln't be hurt in a dark environment. This is realized by the average brightness calculation based on the pictures shot by the camera. 

# Diagram
![Circuit](https://user-images.githubusercontent.com/114015725/205458611-52b57a95-9999-4930-9a0c-e5fe758abfb6.jpg)
