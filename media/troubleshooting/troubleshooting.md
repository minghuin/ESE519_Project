# Temperature Measuring Problem
At first, the data obtained by the temperature sensor is nor correct, which is because of the intrinsic setting on different sensors. We measure the outdoor temperature and indoor temperature as anchor to adjust the algorithms in the code, resulting in accurate temperature measuring.
```
float temp = 27-(result-0.706)/0.003021;
```
