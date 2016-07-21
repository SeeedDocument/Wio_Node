# Wio Node
***
## Introduction

Building IoT project is exciting, as you can connect almost everything around you and control them. However it is also not easy to build IoT applications since it requires a lot of hard works such as hardware programming, jump wires, soldering etc.Even a well trained user would spend hours to hanlde all the work, let alone beginers. In order to simplify the development of IoT project, Seeed initiated **[Wio Link](http://www.seeedstudio.com/wiki/Wio_Link)** on **[kickstarter](https://www.kickstarter.com/projects/seeed/wio-link-3-steps-5-minutes-build-your-iot-applicat?ref=nav_search)** and it turn out a big sucess.The slogen on kickstarter well defined the main feature of Wio link:3 steps. 5 minutes. Build your own IoT applications!It is simple,it is fast buiding,however it is not ideal for all conditions.

What if we only need 2 grove connectors? What if there is limited space in the appication but Wio Link is over sized? What if we want to cost down? So right after we released Wio Link, a micro and economic solution was put on schedule,for months Seeeder has redesigned and optimized the WiFI board and here it is,the new member of Wio family---**Wio Node**.

![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Front%26Back.png)

Just like the meaning of its name, Wio Node is truly a WiFi dot that connect things in IoT project. If Wio Link is big brother, Wio node must be the little brother in the Wio family coz this cute little guy is only quarter size of Wio link while intergrates all the basic features of Wio Link.

The ecosystem of Wio Node also consists of Open Hardware **Wio Node board**, **Open Source Wio Link Mobile App** and **Open Source IoT Server implementation**. So the software platform for Wio Link is also available for Wio Node.


[![Get one now](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/300px-Get_One_Now_Banner.png)](https://www.seeedstudio.com/Wio-Node-p-2637.html)

## Features
- No hardware programming or No breadboard or No jumper wires or No soldering required.
- A lot of Grove modules are supported (Check the list in Mobile App).
- Plug-n-Play Grove Modules
- Visual configuration instead of microcontroller programming.
- Update automatically via cloud compiling and OTA.
- Bring Realworld to Virtual platform. All sensors become virtual RESTful API.
- Android & iOS Apps to manage Wio Node.
- IFTTT supported by Seeed's Channel
- CE/FCC/TELEC Certified for core module ESP-WROOM-02

## Specifications
|General||Power Management||
|:---|---|---|---:|
|**Size**|28mm * 28mm|**DC Current Per I/O Pin**|12mA|
|**Crystal**|26MHz|**Input Voltage (MicroUSB)**| 5V|
|**Flash Memory**|4MBytes (W25Q32B)|**Input Voltage (Battery holder)**|3.4~4.2V|
|**Wi-Fi Network Protocol**|802.11b/g/n|**Output DC Current**|1000mA MAX
|**Wi-Fi Encryption Technology**|WEP/TKIP/AES|**Operating Voltage**|3.3V|
|**Expansion Grove Connector1**|UART0/I2C0/D0 |**Charge Current**|500mA MAX|
|**Expansion Grove Connector2**|Analog/I2C1/D1|

## Hardware Overview

No.|Name|Function|No.|Name|Function|
:---:|:---|---|:---:|---|:---|
1|	**Function Button**| Set Wio Node Mode|5|	**Port0**|	UART/I2C0/D0
2|	**ESP8266**|	MCU Module|6|	**Port1**|	Analog/I2C1/D1
3|	**Reset Button**|	Reset the MCU|7|**JST 2.0 Port**|	Power supply from battery
4|	**Micro USB**|	Power Supply|

![](https://raw.githubusercontent.com/SeeedDocument/Wio_Node/master/pictures/Hardware%20Overview.png)

### Bonus!
Wio Node has an inbuilt LiPo battery charger, so you can charge 3.7v LiPo battery through JST 2.0 Port when USB is connecting.

Note!
- Please handle the USB micro type-B socket gently, or you may break the socket apart from the board.
- Battery is not included in the package. But we have arranged plenty of choices for you in [Bazzar](https://www.seeedstudio.com/s/battery.html).


## Get Started
Let us build a very basic LED application with Wio Node,in this application you will be able to control LED by your smartphone in about 5 minutes.Before we start, please make sure you have below things on hand:（need pictures and links later）
- Wio node
- Smartphone (Android OS version 4.1 or advanced, iOS version 7 or advanced.)
- Grove-Led by Seeed
- USB cable

### Step 1: Install Android/iOS App
You need to install the Wio Link App to manage and configure your Wio Node devices.

Download the Android or iOS App and install. Or you can go to app store of Apple or Google market and search "Wio Link",you will find it.
|Android|iOS|
|:---:|:---:|
|[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20core%20icon.png)](https://play.google.com/store/apps/details?id=cc.seeed.iot.ap)|[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20core%20icon.png)](https://itunes.apple.com/us/app/wio-link/id1054893491?mt=8)|

Note!
Make sure your Android OS version is 4.1 or advanced, iOS version is 7 or advanced.
### Step 2: Create your Account
- If it is your first time to use Wio APP,you may need to sign up first.
- If you already have an account, check the server location before logging in, a wrong server location may lead to falure when connecting to Wio Node.

![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/sign%20in%2Blog%20in%2Bchoose%20server.png)
### Step3: Connect Wio Node WiFi AP
- Push and hold the CONFIG button until the blue LED turns into breathing mode (i.e blinking with fade in & fade out effect). It means that Wio node has turned to configuration mode successfully and can be detected by the Wio App.
![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Confiture%20button.png)
- Push "Add your first Device".
- Choose Wio Node
- "Go to wifi list" will lead you to the wifi setting interface of yoour smartphone.

![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Connect%20to%20Wio%20node%201.png)

- If you have successfully made the blue LED turn into breathing mode, you will find the wio node in the wifi list, connect to it!(Usually it is not called wio node in the wifi list, in the exsample, mine is Wio_091016, you may find one named wio_xxxxxx in your list.)
- Once connected, you will receive a notice, then you can go back to the app 
- Next step is connecting to the wifi of your home or company.

![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Connect%20to%20Wio%20node2.png)

- If there is password pf the wifi you want to connect,it may require you to enter the password
- Consider that you may need to connect more than 1 wio node in the future,a special name will make you distinguish them from each other easily.

![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Connect%20to%20Wio%20node3.png)
### Step 4: Virtually interconnect modules with Wio Node and down load firmware
- Click the Wio Node and you will be in the main interface.
- There are 2 grove connectors, select the left one(D0).
- Because LED is output devices. choose output category
- Find the icon that looks like a bulb,choose it.
- Then you will find the bottom rectangle button becomes red and "View API" becomes "Update Firmware".Choose "Update Firmware"

![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Connect%20modules%20with%20Wio%20node.png)

- Since you selected the D0 port to connect with LED in the APP, you need to connect the real Grove-LED to D0 port of Wio Node too.

![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Wio_Node_Grove_LED.JPG)

### Step 5: Test application using APIs

## Application Ideas
|Irrigation control system |The internet of led wall | Dog feeding machine|
|---|---|---|
|[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/2.png)](http://www.seeed.cc/project_detail.html?id=1274)    |[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/1.png)](http://www.seeed.cc/project_detail.html?id=1594) |![](https://raw.githubusercontent.com/SeeedDocument/Wio_Node/master/pictures/3.png)|

## FAQ

## Resources

- [Grove - 3-Axis Analog Accelerometer Eagle File](https://github.com/SeeedDocument/Grove_3_Axis_Analog_Accelerometer/raw/master/resource/Grove_-_3-Axis_Analog_Accelerometer_Eagle_File.zip)
- [3-Axis Analog Accelerometer Library](https://github.com/SeeedDocument/Grove_3_Axis_Analog_Accelerometer/raw/master/resource/AnalogAccelerometer.zip)
- [github repository for 3-Axis Analog Accelerometer](https://github.com/Seeed-Studio/Accelerometer_ADXL335)
- [ADXL335 datasheet.pdf](https://github.com/SeeedDocument/Grove_3_Axis_Analog_Accelerometer/raw/master/resource/ADXL335_datasheet.pdf)


## Help us to make it better

<iframe style="height: 600px; width: 500px; margin: 10px 0 10px;" allowTransparency="true" src="https://www.surveymonkey.com/r/5P6WC89" frameborder="0"></iframe>




