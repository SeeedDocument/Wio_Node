# Wio Node
## Introduction 
----
Building IoT projects is exciting, as you can connect almost everything around you and control them. However sometime it is not easy to build IoT applications since it requires a lot of hard works, such as hardware,  programming, jump wires and soldering etc. Even a well-trained user would spend hours to handle all the work, let alone beginners. In order to simplify the development of IoT project, Seeed launched **[Wio Link](http://www.seeedstudio.com/wiki/Wio_Link)** on **[kickstarter](https://www.kickstarter.com/projects/seeed/wio-link-3-steps-5-minutes-build-your-iot-applicat?ref=nav_search)** and it turn out a big success. The slogan on Kickstarter well defined the main feature of Wio link: 

**3 steps. 5 minutes. Build your own IoT applications!** 

It is so simple, it is fast building, however it is not ideal for all conditions.
What if we only need 2 grove connectors? What if there is limited space in the application but Wio Link is over sized? What if we want to cost down? So right after we released Wio Link, a micro and economic solution was put on schedule, for months Seeeder has redesigned and optimized the Wi-Fi board and here it is, the new member of Wio family---**Wio Node**.

[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Front%26Back.png)](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Front%26Back.png)

Just like the meaning of its name, Wio Node is truly a Wi-Fi node that connect things in IoT project. If Wio Link is big brother, Wio Node must be the little brother in the Wio family coz this cute little guy is only quarter size of Wio link while integrates all the basic features of Wio Link.

The ecosystem of Wio Node also consists of Open Hardware **Wio Node board**, **Open Source Wio Link Mobile App** and **Open Source IoT Server implementation**. So the software platform for Wio Link is also available for Wio Node.

[![Get one now](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/300px-Get_One_Now_Banner.png)](https://www.seeedstudio.com/Wio-Node-p-2637.html)

## Features
----
- No hardware programming or No breadboard or No jumper wires or No soldering required.
- A lot of Grove modules are supported (Check the list in Mobile App).
- Plug-n-Play Grove Modules
- Visual configuration instead of microcontroller programming.
- Update automatically via cloud compiling and OTA.
- Bring Real-world to Virtual platform. All sensors become virtual RESTful API.
- Android & iOS Apps to manage Wio Node.
- IFTTT supported by Seeed's Channel
- CE/FCC/TELEC Certified for core module ESP-WROOM-02

## Specifications
----
|General|Value|Power Management|Value|
|:---|---|:---|---:|
|**Size**|28mm * 28mm|**DC Current Per I/O Pin**|12mA|
|**Crystal**|26MHz|**Input Voltage (Micro USB)**| 5V|
|**Flash Memory**|4MBytes (W25Q32B)|**Input Voltage (Battery holder)**|3.4~4.2V|
|**Wi-Fi Network Protocol**|802.11b/g/n|**Output DC Current**|1000mA MAX
|**Wi-Fi Encryption Technology**|WEP/TKIP/AES|**Operating Voltage**|3.3V|
|**Expansion Grove Connector1**|UART0/I2C0/D0 |**Charge Current**|500mA MAX|
|**Expansion Grove Connector2**|Analog/I2C1/D1|

## Application Ideas
----
Wio Node is well designed to provide simple and economic Wi-Fi solutions for projects like:

- Smart Home
- Intelligent environmental monitoring
- Funny Toys
- Web of Things
- Internet of Things

In fact, we have already designed many projects in our [**recipe**](http://www.seeed.cc/projects.html?t=Wio), come and visit it to find some interesting projects or even share you own projects, I am sure it will gain a lot of fans for you ~

|Irrigation control system |The internet of led wall | Dog feeding machine|
|---|---|---|
|![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/2.png)|![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/1.png)|![](https://raw.githubusercontent.com/SeeedDocument/Wio_Node/master/pictures/3.png)|
|[MAKE IT NOW](http://www.seeed.cc/project_detail.html?id=1274)    |[MAKE IT NOW](http://www.seeed.cc/project_detail.html?id=1594) |[MAKE IT NOW](http://www.seeed.cc/project_detail.html?id=1066)|

|Kickstarter Monitor|MIssing Call Monitor|Boss Key|
|---|---|---|
|![](https://raw.githubusercontent.com/SeeedDocument/Wio_Node/master/pictures/4.png)|![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/5.png)|![](https://raw.githubusercontent.com/SeeedDocument/Wio_Node/master/pictures/6.png)|
|[MAKE IT NOW](http://www.seeed.cc/project_detail.html?id=1081)    |[MAKE IT NOW](http://www.seeed.cc/project_detail.html?id=1059) |[MAKE IT NOW](http://www.seeed.cc/project_detail.html?id=1077)|


!!!Note
    Some of the recipes are made by Wio Link, you can replace it with a Wio Node.

## Hardware Overview
----

[![](https://raw.githubusercontent.com/SeeedDocument/Wio_Node/master/pictures/Wio_Node_illustrate.jpg)](https://raw.githubusercontent.com/SeeedDocument/Wio_Node/master/pictures/Wio_Node_illustrate.jpg)

|No.|Name|Function|
|---|----|--------|
|1  |Function|Set Wio Node working mode|
|2  |ESP8266|Microcontroller based on ESP8266|
|3  |Reset|Reset the device|
|4  |Micro USB|Supply the device and charge the battery|
|5  | Battery Holder|A jst2.0 connector, connect a 3.7V Li-Battery|
|6  | Analog/I2C1/D1|Grove port, you can connect a Digital/I2C/Analog type Grove module|
|7  | UART/I2C0/D0|Grove port, you can connect a UART/I2C/Digital type Grove module|

###Status LEDs

Near to the FUNCTION button there're 2 status Leds, a blue one and a red one. The BLUE led is the network status indicating led. It has the following blink patterns:

- breathing Under configuration mode
- blink twice quickly then off 1s requesting IP address from router
- blink once quickly then off 1s connecting to the server
- on 1s then off 1s The node is online
- on constantly the node is dead for not getting IP or not connecting to server.
- blink quickly (on 100ms then off 100ms) OTA

!!!Note
    The BLUE led is attached to GPIO2 which is also the TX pin of UART1. When downloading firmware, the UART1 dumps the data transmitting on UART0 by instinct. So the BLUE led will blink while downloading firmware. After startup the GPIO2 will be configured as a GPIO not TX of UART1.

The RED led is another status led which indicates the power status of Grove modules. All the six Grove interface's VCC converge together and can be controlled with GPIO 15. When the node is in deep sleep mode, all the grove modules lose their power too. The RED led will light on when Grove modules are powered and will go off when Grove modules aren't powered.


### Bonus!
Wio Node has an inbuilt LiPo battery charger, so you can charge 3.7v LiPo battery through JST 2.0 Port when USB is connecting.

!!!Note
    * Please handle the USB micro type-B socket gently, or you may break the socket apart from the board.
    * Battery is not included in the package. But we have arranged plenty of choices for you in [Bazzar](https://www.seeedstudio.com/s/battery.html).



## Get Started
----
Let us build a very basic LED application with Wio Node, in this application you will be able to control LED by your smartphone in about 5 minutes. Before we start, please make sure you have below things on hand:

|Wio Node|Grove - LED|Micro USB Cable|
|--------|-----------|---------------|
|![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20Node2.png)|![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Red%20LED.jpg)|![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/48cmUSBc.jpg)|
|[GET ONE NOW](https://www.seeedstudio.com/Wio-Node-p-2637.html)|[GET ONE NOW](https://www.seeedstudio.com/Grove-Red-LED-p-1142.html)|[GET ONE NOW](http://www.seeedstudio.com/Micro-USB-Cable-48cm-p-1475.html)|


!!!NOTE
    * A smartphone is needed as well (Android OS version 4.1 or advanced, iOS version 7 or advanced)
    * Grove - LED include a Grove cable already
### **STEP 1:** Install Android/iOS App
You need to install the Wio Link App to manage and configure your Wio Node devices.

Download the Android or iOS App and install. Or you can go to app store of Apple or Google market and search "Wio Link", you will find it.

|[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Android%20Robot%20new.jpg)](https://play.google.com/store/apps/details?id=cc.seeed.iot.ap)|[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Apple%20new.jpg)](https://itunes.apple.com/us/app/wio-link/id1054893491?mt=8)|
|:---:|:---:|
|[Get Android App](https://play.google.com/store/apps/details?id=cc.seeed.iot.ap)|[Get iOS App](https://itunes.apple.com/us/app/wio-link/id1054893491?mt=8)|

!!!Note
    Make sure your Android OS version is 4.1 or advanced, iOS version is 7 or advanced.

### **STEP 2:** Create your Account
- If it is your first time to use Wio APP, it may require GPS authorization, please approve it, then sign up.
- If you already have an account, check the server location before logging in.

!!!Note
Please pay attention to the server location, because wrong server location will lead to failure when connecting to Wio Node.

[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/sign%20in%2Blog%20in%2Bchoose%20server.png)](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/sign%20in%2Blog%20in%2Bchoose%20server.png)

### **STEP 3**: Connect Wio Node Wi-Fi AP
- Push and hold the CONFIG button until the blue LED turns into breathing mode (i.e. blinking with fade in & fade out effect). It means that Wio Node has turned to configuration mode successfully and can be detected by the Wio App.
[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Confiture%20button.png)](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Confiture%20button.png)
- Push "Add your first Device".
- Choose Wio Node
- "Go to Wi-Fi list" will lead you to the Wi-Fi setting interface of your smartphone.

[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Connect%20to%20Wio%20node%201.png)](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Connect%20to%20Wio%20node%201.png)

- If you have successfully made the blue LED turn into breathing mode, you will find the Wio Node in the Wi-Fi list, connect to it!(Usually it is not called Wio Node in the Wi-Fi list, in the example, mine is Wio_091016, you may find one named wio_xxxxxx in your list.)
- Once connected, you will receive a notice, then you can go back to the app 
- Next step is connecting to the Wi-Fi of your home or company

[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Connect%20to%20Wio%20node2.png)](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Connect%20to%20Wio%20node2.png)

- If there is password pf the Wi-Fi you want to connect, it may require you to enter the password
- Consider that you may need to connect more than 1 Wio Node in the future, a special name will make you distinguish them from each other easily.

[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Connect%20to%20Wio%20node3.png)](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Connect%20to%20Wio%20node3.png)
### **STEP 4:** Virtually interconnect modules with Wio Node and update firmware
- Click the Wio Node and you will be in the main interface.
- There are 2 grove connectors, select the left one (D0).
- Because LED is output devices. Choose output category
- Find the icon that looks like a bulb, choose it.
- Then you will find the bottom rectangle button becomes red and "View API" becomes "Update Firmware". Choose "Update Firmware"

[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Connect%20modules%20with%20Wio%20node.png)](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Connect%20modules%20with%20Wio%20node.png)

- Since you selected the D0 port to connect with LED in the APP, you need to connect the real Grove-LED to D0 port of Wio Node too.

[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Wio_Node_Grove_LED.JPG)](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/Wio%20App/Wio_Node_Grove_LED.JPG)

### **STEP 5**: Test application using APIs
- Now that  you have successfully connect the LED to Wio Node, click "View API" to check the API of Wio Node
- Input "1" or "0" in the "Test Request" area, and click "Post" button and see what will happen.

[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/change%20the%20valure%20to%20see%20what%20will%20happen.png)](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/change%20the%20valure%20to%20see%20what%20will%20happen.png)


## Get started with IFTTT & DoButton
----
Dont't know how to code? Don't worry, with the help of [IFTTT](https://en.wikipedia.org/wiki/IFTTT), even if you know nothing about coding, you are still able to build some simple projects.

IFTTT is an abbreviation of "If This Then That", it is a free web-based service that allows users to create chains of simple conditional statements, called "recipes", which are triggered based on changes to other web services such as Gmail, Facebook, Instagram. How does IFTTT work with Wio Node？ As you can see in below pictures, seeed provided cloud service at wio.seeed.io, which can interchange data and send instructions to IFTTT and Wio Node. So by creating some simple recipe, you are able to hack things without coding.

![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/WioLink-Workshop.png)

If you don't have an IFTTT account, click [here](https://ifttt.com/join) to sign up.

If you already have an IFTTT account,click [here](https://ifttt.com/recipes/search?q=seeed) to connect with Seeed, or search Seeed at IFTTT website. There you will find 9 recipes by Seeed to teach you how to us e IFTTT.
[![](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/IFTTT%20recipes.png)](https://github.com/SeeedDocument/Wio_Node/raw/master/pictures/IFTTT%20recipes.png)
What is DoButton? DoButton is one of IFTTT's application that empowers you to create your own personalized button with just a tap, it is very suitable for building IoT projects and control it through your smartphone, here are two examples to show you how to use IFTTT&DoButton to make useful applications.

### Example:

|**IFTTT**|**DoButton**|
|:---|:---|
|[**Recipe**][DIY an Automatic Garden Irrigation without coding](http://www.seeed.cc/project_detail.html?id=1080)|[**Recipe**][How to feed your pets when you're not home](http://www.seeed.cc/project_detail.html?id=1066)|
|[**Video**][How to use ITFFF](https://vimeo.com/148590984)|[**Video**][How to use DoButton](https://vimeo.com/146988454)|



## Guide for advanced users
----
Feel those examples too simple? Wanna make more complicated proejects? Here are the best guides for advanced users to hack things with Wio nude. By these guides, advanced users are able to know more detail information about Wio Node, deploy private server, even write module driver for Wio Node. 

[![](https://raw.githubusercontent.com/SeeedDocument/Wio_Node/master/pictures/GOTO_ADVANCED_GUIDE.png)](https://github.com/Seeed-Studio/Wio_Link/wiki)

The guide covers:

- API Reference
- Server Deployment Guide
- Advanced User Guide
- How to write module driver for Wio Link?



!!!Note
    The guide is writen for Wio Link, but applies to Wio Node as well.

 
## FAQ
----
Here are some questions that we usually received from new users. If you have any other issues when you are using Wio Node or other Wio products, welcome to the [Community of Wio](http://www.seeed.cc/topics.html?t=Wio) where there are many professional users waiting to give you advices and also many advanced users providing plenty of ideas on how to use Wio products! 

**1. What's the difference between Wio Node and Wio Link?**

Wio Node is like mini Wio Link, it is only quarter size of Wio Link and much cheaper. Despite the size and price, Wio Node still has full function of Wio Link. For those who prefer smaller size to more grove connectors. Wio node is the best choice.

**2. What should I do if can't connect with Server?**

Log out and check if you chose wrong server before logging in. If you are not in China Mainland, please choose global server.

**3. Fail to configure Wio Node and can't find Wio Node in wifi list?**

Pay attention to the blue LED. Make sure it is in breathing mode (blinking with fade in & fade out effect, it is a very unique mode, very easy to recognize) before any further steps. Only the LED in breathing mode can Wio Node be found in WiFi list.

**4. If I want to connect more than 1 I2C devices, what should I do?**

[Grove-I2C hub](https://www.seeedstudio.com/s/I2C%20hub.html) can branch 1 I2C port into 4. Come to [Bazzar](https://www.seeedstudio.com/s/I2C%20hub.html) to get one!

**5. Can I change Wio Node into sleep mode?**

Yes, please check the last API, where you can command Wio Node into sleep mode.

## Resources
----
- **Documentation and references**
    - [API Reference](http://seeed-studio.github.io/Wio_Link/)
    - [Server Deployment Guide](https://github.com/Seeed-Studio/Wio_Link/wiki/Server%20Deployment%20Guide)
    - [How to write module driver for Wio Link](https://github.com/Seeed-Studio/Wio_Link/wiki/How-to-write-module-driver-for-Wio-Link%3F)
- **Software**
    - [Sourcecode on **Github**](https://github.com/Seeed-Studio/Wio_Link)
- **Hardware**
    - [Schematic File in **PDF**](https://github.com/SeeedDocument/Wio_Node/raw/master/Recources/Wio%20Node%20v1.0.pdf)
    - [Schematic File in **Eagle**](https://github.com/SeeedDocument/Wio_Node/raw/master/Recources/Wio_Node_Schematics.zip)
- **Certificate**
    - [CE/FCC/TELEC Certified(only) for core module ESP-WROOM-02](https://github.com/SeeedDocument/Wio_Node/raw/master/Recources/CE-FCC-TELEC_Certified(only)_for_core_module_ESP-WROOM-02.zip)




## Help us to make it better
----
<iframe style="height: 600px; width: 500px; margin: 10px 0 10px;" allowTransparency="true" src="https://www.surveymonkey.com/r/JD8KXBS" frameborder="0"></iframe>


