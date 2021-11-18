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




