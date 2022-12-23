# ESE519_Project

# Design
An elect-rooster is an intelligent clock system. Current time and temperature are shown on the screen of Pico4ml and the brightness of the screen will be adjusted automatically based on the environment. The rooster will crow every morning when it sees the light. 
![05AC778D-8127-456B-AF4F-78B8116FB1DC_1_102_a](https://user-images.githubusercontent.com/114015725/209373902-898495f5-73e6-4c86-8a3a-431418999f2f.jpeg)


## Feature
Initialization of current time is realized by WiFi module ESP 8266.

Instant temperature is collected by the temperature sensor on Pico4ml. 

Another interesting feature is that the brightness of the screen would automatically adjust based on the environment. It will go dark in a dark environment, so your eyes won't get hurt. This is realized by the average brightness calculation based on the pictures shot by the camera. 


## Demo

https://github.com/ApolloW1/ESE519_Project/blob/main/media/demos/IMG_0537.gif

## Diagram
<img width="416" alt="image" src="https://user-images.githubusercontent.com/114015725/209372855-7c0fa8dc-8ebf-4236-869c-a21c33068fa6.png">



# Materials

Pico4ml

![Pico4ml](https://user-images.githubusercontent.com/114015725/205458189-9b1b5b24-a74c-4aa0-a191-84875c989ed5.jpg)

Buzzer

![Buzzer](https://user-images.githubusercontent.com/114015725/205458210-97050459-0119-4827-a8aa-bbd22abb02c5.jpg)

ESP 8266

![image](https://user-images.githubusercontent.com/114015725/209374495-b5291494-da7f-4a66-b245-02f6b96bf956.png)

Power Bank

![image](https://user-images.githubusercontent.com/114015725/209374758-8889ebb5-f520-4abe-a14f-5af2d1fd0105.png)

# Troubleshooting
## Temperature Measuring Problem
At first, the data obtained by the temperature sensor is nor correct, which is because of the intrinsic setting on different sensors. We measure the outdoor temperature and indoor temperature as anchor to adjust the algorithms in the code, resulting in accurate temperature measuring.
```
float temp = 27-(result-0.706)/0.003021;
```

## Time Accuracy Problem
The time is not accurate when we simply set sleep time to 1000 ms in the code. We then record the difference of 100 s and 1000 s of the program and compare it with the real time to adjust the sleep time, which gives us a relative correct timestemp.
