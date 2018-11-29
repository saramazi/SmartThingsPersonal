# 1. Introduction
This document describes my personal IoT enviornment, settings and rules

# 2. Things
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
+ Xiaomi Smart Strip

# 3. State
+ Home
+ Night
+ Away

# 4. Smartthings
## 4.1. Scene
- Controls Living Room Light, Virtual Air Purifier and Yamaha Music Cast
- Only for Smartapp(Web-core will do everything)

### 4.1.1. Day Scene
* Yamaha -  On, Volume 91
* Virtual Air Purifier - On
* Living Room Light - Off

### 4.1.2. Evening Scene
* Yamaha - On, Volume 81
* Virtual Air Purifier - On
* Living Room Light - On, Level 60

### 4.1.3. Night Scene
* Yamaha - Off
* Virtual Air Purifier - Off
* Living Room Light - Off

### 4.1.4. Lullaby Scene
* Yamaha - On, Volume 81
* Virtual Air Purifier - On
* Living Room Light - On, Level 1

## 4.2. Routine
- Every smartthings routine will do nothing
- Routine is just a trigger to corresponding Web-core piston

### 4.2.1. Good Morning!
### 4.2.2. Good Evening!
### 4.2.3. Good Night!
### 4.2.4. I'm Home!
### 4.2.5. Goodbye!
### 4.2.6. Lullaby

# 5. Web-core
## 5.1. Trigger
### 5.1.1. Presence_01_Home
### 5.1.2. Presence_02_Away
### 5.1.3. ST_Routine_01_Morning
### 5.1.4. ST_Routine_02_Evening
### 5.1.5. ST_Routine_03_Night
### 5.1.6. ST_Routine_04_Home
### 5.1.7. ST_Routine_05_Away
### 5.1.8. ST_Routine_06_Lullaby
### 5.1.9. Schedule_01_Morning
### 5.1.10. Schedule_02_Evening

## 5.2. Bullet
### 5.2.1. Morning
### 5.2.2. Evening
### 5.2.3. Night
### 5.2.4. Home
### 5.2.5. Away
### 5.2.6. Lullaby
