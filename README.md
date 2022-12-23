# ESE519_Project

# Design
An elect-rooster is an intelligent clock system. Current time and temperature are shown on the screen of Pico4ml and the brightness of the screen will be adjusted automatically based on the environment. The rooster will crow every morning when it sees the light. 

## Feature
Initialization of current time is realized by WiFi module ESP 8266.

Instant temperature is collected by the temperature sensor on Pico4ml. 

Another interesting feature is that the brightness of the screen would automatically adjust based on the environment. It will go dark in a dark environment, so your eyes won't get hurt. This is realized by the average brightness calculation based on the pictures shot by the camera. 

## Diagram
![image](https://user-images.githubusercontent.com/114015725/209371673-579a6b6a-68b4-440d-be8e-82d6b97cbbed.png)


# Materials
Buzzer

![Buzzer](https://user-images.githubusercontent.com/114015725/205458210-97050459-0119-4827-a8aa-bbd22abb02c5.jpg)

Pico4ml

![Pico4ml](https://user-images.githubusercontent.com/114015725/205458189-9b1b5b24-a74c-4aa0-a191-84875c989ed5.jpg)

# Demo
<img width="447" alt="demo" src="https://user-images.githubusercontent.com/114015725/205527584-8d51b2d2-5bbf-490a-8a9c-fb7a5c4e3344.png">

# Troubleshooting
## Temperature Measuring Problem
At first, the data obtained by the temperature sensor is nor correct, which is because of the intrinsic setting on different sensors. We measure the outdoor temperature and indoor temperature as anchor to adjust the algorithms in the code, resulting in accurate temperature measuring.
```
float temp = 27-(result-0.706)/0.003021;
```

## Time Accuracy Problem
The time is not accurate when we simply set sleep time to 1000 ms in the code. We then record the difference of 100 s and 1000 s of the program and compare it with the real time to adjust the sleep time, which gives us a relative correct timestemp.
