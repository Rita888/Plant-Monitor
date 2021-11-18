//Building a Plant Monitor//

This is my step by step blog of how I built a plant monitor to record humidity, temperature and soil moisture levels


![Screenshot 2021-11-18 at 14 22 48](https://user-images.githubusercontent.com/93122551/142433200-2e206222-e709-4d8d-af70-6dbaa67e9d7d.png)


This is my plant and I have the oppotunity to look after it for the next few months. 

It is a Common asparagus fern (Asparagus setaceus) Gardener's world.com (2021) noted that it likes bright (out of direct sunlight) areas, minimum of 13°C. The soil needs to be moist but not boggy - allowing any excess water to drain away. In the spring it likes more water and throughtout autumn and winter too much. It needs to tertilised with liquid feed in spring and summer. 
 
  
  The equipment that I need (not all componenets are listed at this time - the list will be added to)
  _Feather Huzzah ESP8266 wifi
  _Raspberry Pi 
  _Moisture Sensor 
  _Jumper Wires 
  _Resistors 
  _usb cable to power up 
  _Metal nails 
  _Breadboard
  _Soldering Iron and Soldering 

Step 1 -
-I need Arduino IDE to write code and connect to the Feather Huzzah
-Download and install MQTT Explorer - this is where I will be able to see my live data (note that this data is not stored - only displays live data) 
-GitHub account to store my project and data 

Step 2 -
Setting Feather Huzzah ESP8266 by opening up Arduino and install CP2104 driver and board package 
Add Additional Board manager URLs section that will recognise my board by download the right package to my laptop - otherwise my laptop doesn't know anything about the board

Step 3
-Sensing soil will use Arduino Nails Soil Sensor which works on a principle that resistance between two nails are measured at a distance apart - therefore the further the nails apart the less resistance there is, closer together the greater the resistance. It is important that once the nails are set in the plant pot (soil) that the space between the nails remains the same for as long as possible. 

Note to self: challenging to choose the nails as these will depend on the length, depth of soil, type of soil. I was given the nails and no further questions asked at this time of the assignment. This might be an issue as the nails might corrode overtime and the data might be invalid. Time will show but something to consider for any future projects.


![Screenshot 2021-11-18 at 14 41 19](https://user-images.githubusercontent.com/93122551/142436532-fc4bcd4c-b1af-4b48-ae25-169c1a482b8a.png)

I connected my Feather Huzzah and DHT22 Temperature / Humidity sensor to the CASA Plant monitor shield that was provided by Professor Duncan Smith at UCL (2021) for Connected Environments MSc Programme. I connected all of the required components such as the resisters (to stop it buirning up as the electirical current is 5V) by soldering these together. Unfortunately, because I am all over the place at this time and place I didn't take a good photograph of the final product. 


Step 4
- the code was provided to me, and I had to change two portions of it to make it work and to display it (end at the end of this blog – the code used is provided along with amendments)
- First was the WIFI details - I used Arduino Secrets to protect Wi-Fi details and not display it to public on GitHub. This was hidden away. 
- Secondly, I had to provide the Wi-Fi details in the code so that I was board would be connected to WIFI and transmit the collected data to the MQTT server and later save that data to raspberry pi. 
- Thirdly, to identify my plant I changed my name to my Student UCL letters for easier identification
- Fourthly, I connected to MQTT server that started to display my live data.

![image](https://user-images.githubusercontent.com/93122551/142456208-4ea6c2d2-420e-41f0-ba90-7edba853a985.png)

![image](https://user-images.githubusercontent.com/93122551/142456247-9cff6719-2280-4a20-9dc6-588e464eee55.png)


Step 5
-once my data started to get published on the MQTT, I needed to set up Raspberry Pi to store my collected data. 
- I followed instructions that were set out by Professor Duncan Smith to set up the initial stage of Raspberry Pi (RPi)

![image](https://user-images.githubusercontent.com/93122551/142456282-101764a3-7db0-4450-a12c-b59d245568d9.png)


-I then followed instructions to download InfluxDB on RPi to then show case my data on Grafana (open-source data viewer) 

I was able to view my data on Grafana however due to limited time and deadline, I am not able to show off beautiful graphs. 


Few questions to answer after the sensors were deployed

What are the negative consequences of the devices being prototyped? 

Lack of initial research and not knowing how to monitor the plants correctly. Further research should have been done prior to building the sensor board. 

In what environments will the users employ the device?

In my field of work, I would want to deploy these kinds of sensors on the green roofs and living walls in the urban context. As the National Planning Policy sets out for new developments to include biodiversity enhancements. Historically shown that the lack of proper maintenance or management that negatively impacted these new enhancements by no proper irrigation, no fertilization, no protection from high or low temperatures. By employing these sensors and gathering data overtime, it can help with long term management of these biodiversity enhancements. 

Will different users interact with the device differently? 

Yes, everyone idea of how the world should be is different therefore users might want to gather data differently or display it to their preferences to perhaps sell their data or product as such sugar coating their product. 

Does the data tell the truth?

I hope so. I didn’t have the chance to ground truth the sensors by measuring temperature, humidity and soil moisture using other methods – therefore for all I know these sensors might be recording invalid data. 

Will someone hack my sensor? 

Hopefully not but something to think about in our data rich world. Something for me to think about!

Could someone tamper with the device to change its readings? 

I don’t know – my knowledge is very limited and I hope that over time I will learn more about devices, how to protect them and how to manage/store data. 

Does it matter where the device is located? 

Yes, preferably away from open water where it this can damage the sensors and the cause electrical circuit to break, and the data will not be collected therefore ending this project before its intended end. 
Also, I would like to be in an enclosed structure however this needs to be designed so that the temperature sensor collects the ‘correct data’ so choosing the right material is vital. The building material needs to be waterproof, provide structure and be ‘breathable’ to allow air flow. 

What are the unintended consequences of this device that you can imagine?

I am not sure how to answer this question. More to follow.


Self-criticism: Coming from a non-engineering background and reading limited books for this project, I have lots of catching up to do. 
-	New Laptop with plenty of storage to save all the programmes needed for future projects and saving projects on the laptop as well as external source such as GitHUb. 
-	Extremely important to do background reading and further reading each week. 
-	Each week recap on the lecture notes after completing the essential reading to re-enforce the learning progress.
-	DO NOT leave everything until the last minute – seek help straight away. 
-	DO NOT overload yourself with work as it is the path of least resistance – allow yourself to grow! There is a reason why you wanted to study again!


References 

Arduino (2015). Starter Kit Project Book. Arduino 

CASA at UCL (2021). Plant Monitor workbook (available digitally). University College London, London.

