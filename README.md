# ESE519_Project

# Design
A intelligence clock system is designed with the screen of Pico4ml to show time and temperature information. The time should be initialized every time when it's connected to power as Pico4ml does not have its internal clock. 

## Feature
The basic feature is that the alarm will ring on the setting time. 

Besides, the temperature information is collceted by the temperature sensor of Pico4ml itself. 

Another interesting feature is that the brightness of the screen would automatically adjust based on the current environment, so your eyes wouln't be hurt in a dark environment. This is realized by the average brightness calculation based on the pictures shot by the camera. 

## Diagram
![Circuit](https://user-images.githubusercontent.com/114015725/205458611-52b57a95-9999-4930-9a0c-e5fe758abfb6.jpg)

## Circuit
![Circuit (1)](https://user-images.githubusercontent.com/114015725/205458220-78c38008-cb0d-481e-9366-30cf82506b97.jpg)

# Materials
Buzzer

![Buzzer](https://user-images.githubusercontent.com/114015725/205458210-97050459-0119-4827-a8aa-bbd22abb02c5.jpg)

Pico4ml

![Pico4ml](https://user-images.githubusercontent.com/114015725/205458189-9b1b5b24-a74c-4aa0-a191-84875c989ed5.jpg)



# Troubleshooting
## Temperature Measuring Problem
At first, the data obtained by the temperature sensor is nor correct, which is because of the intrinsic setting on different sensors. We measure the outdoor temperature and indoor temperature as anchor to adjust the algorithms in the code, resulting in accurate temperature measuring.
```
float temp = 27-(result-0.706)/0.003021;
```

## Time Accuracy Problem
The time is not accurate when we simply set sleep time to 1000 ms in the code. We then record the difference of 100 s and 1000 s of the program and compare it with the real time to adjust the sleep time, which gives us a relative correct timestemp.
