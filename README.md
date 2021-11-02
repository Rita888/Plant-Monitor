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

//connect to wifi first (connects to CE lab) change if location has changed

#include <ESP8266WiFi.h>

const char* ssid = "CE-Hub";
const char* password = "()c454,w1f1";
const char* host = "iot.io";

void setup() {
  Serial.begin(115200);
  delay(100);

  //starting to connect to wifi network
  Serial.println();
  Serial.print("Connecting to ");
  Serial.println(ssid);
  WiFi.begin(ssid, password);

while (WiFi.status() != WL_CONNECTED) {
  delay(500);
  Serial.print(".");
}

Serial.println("");
Serial.println("WiFi connected");
Serial.println("IP address: ");
Serial.println(WiFi.localIP());
}

void loop() {
  // main code here, to run repeatedly:
  delay(5000) ;
  
 Serial.println("-------------------------------------");
 Serial.print("Connecting to ");
 Serial.println(host);

  // use WiFiClient class to create Tranmission Control Protocol (TCP) 
  WiFiClient client;
  const int httpPort = 80;
  if (!client.connect(host, httpPort)) {
    Serial.println("connection failed");
    return;
  }
//Creating a Universal Resource Identifier (URI) for the request
String url = "/data/index.html";
Serial.print("Requesting URL: ");
Serial.println(host + url);

// This will send the request to the server
client.print(String("GET ") + url + " HTTP/1.1\r\n" +
"Host: " + host + "\r\n" +
"Connection: close\r\n\r\n");

delay(500);
//read all the lines of the reply from server and print them to server
while(client.available()){
  String line = client.readStringUntil('\r');
  Serial.print(line);
}

Serial.println();
Serial.println("closing connection");
}


#include <ESP8266WiFi.h>
#include <ezTime.h>

const char* ssid     = "CE-Hub";
const char* password = "()c454,w1f1";

Timezone GB;

void setup() {
  Serial.begin(115200);
  delay(100);

  // We start by connecting to a WiFi network
  Serial.println();
  Serial.print("Connecting to ");
  Serial.println(ssid);
  WiFi.begin(ssid, password);

  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }

  Serial.println("");
  Serial.println("WiFi connected");  
  Serial.println("IP address: ");
  Serial.println(WiFi.localIP());

  waitForSync();

  Serial.println("UTC: " + UTC.dateTime());

  GB.setLocation("Europe/London");
  Serial.println("London time: " + GB.dateTime());  

}

  void loop() {
  delay(1000);
  Serial.println(GB.dateTime("H:i:s")); // UTC.dateTime("l, d-M-y H:i:s.v T")
}
  
