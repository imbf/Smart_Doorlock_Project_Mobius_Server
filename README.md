# Mobius Server Platform for Smart Doorlock
oneM2M IoT Server Platform for Smart Doorlock

## Mobius Version
2.4.x

## Smart Doorlock Introduction
**스마트 도어락**이란 한국전자부품연구원에서 개발한 오픈소스형 서버 플랫폼인 Mobius 2.0을 활용한 **사용자의 완벽한 외출을 도와주는 IoT 플랫폼** 입니다. 자택 현관문 내부에 존재하는 기존의 딱딱한 도어락 본체는 제거하고 그 자리에 터치식 디스플레이를 설치하여 사용자에게 외출시에 필요한 다양한 정보를 제공하고 집안의 가전들을 등록 및 제어할 수 있는 기능을 가진 **IoT 플랫폼** 입니다.

스마트 도어락의 **사진**은 다음과 같습니다.

<img width="964" alt="스마트도어락 사진" src="https://user-images.githubusercontent.com/47495187/75683405-66783000-5cda-11ea-84b5-a8f3e89a70cf.png">

## Development Period

**2019.04 ~ 2019.10.11**

## Award

제3회 (전자부품연구원)KETI Mobius 2.0 IoT Service Developer Contest에서 전자부품연구원장상(2등상)

## Smart Doorlock Functionality

- **사용자의 스마트폰에 입력된 메모를 표시하는 기능**
- **사용자가 살고 있는 지역의 날씨 및 미세먼지를 표시하는 기능**
- **기본적인 도어락(문열기, 비밀번호 변경)등의 기능**
- **등록된 가전(ADN_AE)의 상태를 확인 및 제어하는 기능**
- **스마트 도어락 만의 특별한 출입관리 프로세스를 통한 일회용 출입관리 프로세스 기능**

## Expected effect of smart doorlock

- 집안의 전등 및 가스레인지 같은 스마트 도어락에 등록된 가전의 상태를 확인 및 제어 함으로써 **안전 사고 예방을** 도와준다.
- 외출 시에 현관문에서 오늘의 날씨 및 미세먼지를 사용자에게 알려주어 옷차림은 알맞게 입었는지 마스크는 꼈는지 등의 외출준비를 도와줍니다. 이로써 **사용자의 번거로움을 없애 삶의 질을 향상**시킵니다.
- 스마트 도어락의 **특화된 일회용 출입관리 프로세스**를 통해서 집에 없는 사용자들도 안심하고 **홈 서비스를** 받을 수 있도록 도와줍니다.

## Smart Doorlock System Architecture

스마트 도어락(version 1.0)의 **시스템 아키텍처**는 다음과 같습니다.

![image](https://user-images.githubusercontent.com/47495187/75686204-2ebfb700-5cdf-11ea-91c4-ce69d147b92b.png)

## Used Technology

- **Node.js** (Mobius (In-CSE))
- **MySQL** (Database)
- **Web Publishing Language** (Smart Doorlock Front-End)
- **C++** (nCube & Tas)
- **AWS SMS Service**

## Used HardWare

- LED Pin
- Adafruit Board + Wifi Module
- Servo Motor
- Keypad
- Model House(Handmade)
- Raspberry Pi + Raspberry Pi Touch Screen(7 Inch)
- Wifi dongle
- ...

## Doorlock Server & (nCube & Tas)

Mobius Server(IN-CSE)와 통신하고 Mobius에 등록된 센서(ADN-AE)를 제어할 수 있는 **Doorlock Server(IN-AE)의 코드가 있는 저장소 주소**는 다음과 같습니다. (https://github.com/imbf/Project_doorklock_Server)

oneM2M IoT 표준의 AE(Application Entity)를 C++을 사용하여 구현했으며, MQTT 프로토콜을 사용하여 사물인터넷 서비스 플랫폼(Mobius)과 연결된 **nCube 및 Tas의 코드가 있는 저장소 주소**는 다음과 같습니다. https://github.com/imbf/Project_nCube_ADN

## Installation
The Mobius is based on Node.js framework and uses MySQL for database.
<div align="center">
<img src="https://user-images.githubusercontent.com/29790334/28322607-7be7d916-6c11-11e7-9d20-ac07961971bf.png" width="600"/>
</div><br/>

- [MySQL Server](https://www.mysql.com/downloads/)<br/>
The MySQL is an open source RDB database so that it is free and ligth. And RDB is very suitable for storing tree data just like oneM2M resource stucture. Most of nCube-Rosemary will work in a restricted hardware environment and the MySQL can work in most of embeded devices.
- [Node.js](https://nodejs.org/en/)<br/>
Node.js® is a JavaScript runtime built on Chrome's V8 JavaScript engine. Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient. Node.js' package ecosystem, npm, is the largest ecosystem of open source libraries in the world. Node.js is very powerful in service impelementation because it provide a rich and free web service API. So, we use it to make RESTful API base on the oneM2M standard.
- [Mosquitto](https://mosquitto.org/)<br/>
Eclipse Mosquitto™ is an open source (EPL/EDL licensed) message broker that implements the MQTT protocol versions 3.1 and 3.1.1. MQTT provides a lightweight method of carrying out messaging using a publish/subscribe model. This makes it suitable for "Internet of Things" messaging such as with low power sensors or mobile devices such as phones, embedded computers or microcontrollers like the Arduino.
- [Mobius](https://github.com/IoTKETI/Mobius/archive/master.zip)<br/>
Mobius source codes are written in javascript. So they don't need any compilation or installation before running.

## Run

아래와 같은 명령어를 입력해서 Node.js 어플리케이션을 실행하세요.
```
node mobius.js
```

<div align="center">
<img src="https://user-images.githubusercontent.com/29790334/28245526-c9db7850-6a43-11e7-9bfd-f0b4fb20e396.png" width="700"/>
</div><br/>

## Library Dependencies
Mobius를 위한 라이브러리 의존성은 다음과 같습니다.
- body-parser
- cbor
- coap
- crypto
- events
- express
- file-stream-rotator
- fs
- http
- https
- ip
- js2xmlparser
- merge
- morgan
- mqtt
- mysql
- shortid
- url
- util
- websocket
- xml2js
- xmlbuilder
