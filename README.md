# Plant-Monitor
CASA0014 Assessment
//step by step set up of the plant monitor
I am given an opportunity to look after Asparagus 'Fern' setaceus. Plant requires damp soil (not waterlogged - not dry)
bright light but not direct sunlight 
Plant monitor will monitor the soil moisture over a period of several months (at least 6 months) 
The monitor needs to be coded to be able to collect data, show it MQTT and save the data (locally and remotely)
![image](https://user-images.githubusercontent.com/93122551/139865886-8ac3103e-0aca-475e-af73-4bbb0b98dc2a.png)
Intergrated Development Environmenta (IDE) was installed and Arduino is used for this project to write the code in order to run the sensor 
ESP8266 Feather Huzzah board was used to connect the soil moisture sensor in order to collect the data
The board has WiFi connection and a power source (USB and an option to install a rechargable battery)
The ASAIR AM2302 SNG120254EC0C7 sensor was added to the board along with two metal nails that will be temporary placed inside the plant pot (the soil) 
The basic principle of the two metal nails is to measure the resistance of the soil between two nais a distance apart. The more mositure there is in the soil the lower the resistance. 
Once the board has been fused with the sensor using the provided sketch ![Screenshot 2021-11-02 at 14 39 45](https://user-images.githubusercontent.com/93122551/139869283-0f9c1491-35bc-402d-82b7-43482f3b36bd.png)
