# 0. Introduction
This document describes my personal IoT enviornment, settings and rules

# 1. Things
+ [Hamony] AC Mode
+ [Hamony] Fan Mode
+ [Hamony] Game Mode
+ [Hamony] Lullaby Mode
+ [Hamony] Movie Mode
+ [Hamony] Music Mode
+ [Hamony] TV Mode
+ Living Room Light
+ Virtual Air Purifier
+ Yamaha
+ Mi Robot Vaccum

# 2. State
+ Home
+ Night
+ Away

# 3. Scene
Controls Living Room Light, Virtual Air Purifier and Yamaha Music Cast

## 3.1. Day Scene
* Yamaha -  On, Volume 91
* Virtual Air Purifier - On
* Living Room Light - Off

## 3.2. Evening Scene
* Yamaha - On, Volume 91
* Virtual Air Purifier - On
* Living Room Light - On, Level 60

## 3.3. Away Scene
* Yamaha - Off
* Virtual Air Purifier - Off
* Living Room Light - Off

## 3.4. Lullaby Scene
* Yamaha - On, Volume 91
* Virtual Air Purifier - On
* Living Room Light - On, Level 1

# 4. Routine
With condition, set scene and turn on/off harmony acitivies

## 4.1. Good Morning!
* Trigger
    - sunrise(core) || alexa
* Scene
    - Day Scene
* State
    - Home

## 4.2. Good Evening!
* Trigger
    - sunset(core) || alexa
* Action
    - Evening Scene
* State
    - Home

## 4.3. Good Night!
* Trigger
    - alexa
* Scene
    - Away Scene
* Action
    - [Hamony] AC Mode - Off
    - [Hamony] Fan Mode - Off
    - [Hamony] TV Mode - Off
    - [Hamony] Movie Mode - Off
    - [Hamony] Game Mode - Off
    - [Hamony] Music Mode - Off
    - [Hamony] Lullaby Mode - Off
* State
    - Night

## 4.4. Lullaby
* Trigger
    - alexa
* Scene
    - Lullaby Scene
* Action
    - [Hamony] Lullaby Mode - On
* State
    - Home

## 4.5. I'm Back!
* Trigger
    - alexa || 핸드폰 위치
* Scene
    - Evening Scene
* State
    - Home

## 4.5. Good Bye!
* Trigger
    - alexa || 핸드폰 위치
* Scene
    - Away Scene
* Action
    - [Hamony] AC Mode - Off
    - [Hamony] Fan Mode - Off
    - [Hamony] TV Mode - Off
    - [Hamony] Movie Mode - Off
    - [Hamony] Game Mode - Off
    - [Hamony] Music Mode - Off
    - [Hamony] Lullaby Mode - Off
* State
    - Away
* Etc
    - 사람 있으면 out mode로 전환하지 않도록
    - 모션센서 구매후에 core piston에서 trigger하도록 필요
    - smartthings의 state만 바꾸고 나머지 작업은 core에서 수행

# 5. Piston
+ SunRise
    * Trigger
        - ifttt 
    * Action
        - run good morning scene
+ SunSet
    * Trigger
        - ifttt 
    * Action
        - run good evening scene
+ I'm back
    * 나중에 조도 센서를 이용해서 morning scene || evening scene 실행 
+ Baby Monitor(TBI)
    * Trigger
        - virtual switch(manual or alexa)
    * Action
        - send http request to foscam
+ Motion Detect(TBI)
    * Condition
        - virtual switch(manual || alexa || night routine || away routine)
    * Trigger
        - Motion detected
    * Action
        - Turn on living room light at 1%
        - wait 10 sec
        - turn off living room light
