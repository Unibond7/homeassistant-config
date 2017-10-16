# Tim's Home Assistant (Driving Ruby crazy ;P)
Configuration files for [Home Assistant](http://homeassistant.io) (Great open source project)

Running HA with a Hassabian install on a Raspberry Pi B2 ver 1.2 with:
* Mosquitto
* Custom [Playstation 4](https://goo.gl/9M44nG) Component

HA Version: 0.54.0

* [Hardware](#hardware)
* [Presence Detection](#presence)
* [Automations](#automations)
* [ToDo](#todo)
* [Lessons Learnt](#lessonslearnt)

## Hardware
* Lights
  * [Philips Hue White ambiance](https://goo.gl/xQEkrF)
  * [Philips Hue White and colour ambiance](https://goo.gl/QCu6Az) - both using [Hue Bridge](https://goo.gl/8crECi)
  * [Osram candle lights (x2)](https://goo.gl/kBqa5r)
* Sensors
  * [Philips Hue Motion Sensor](https://goo.gl/bbGHD4)
  * [Amazon Echo Dot (x2)](https://goo.gl/T7A4kq)
* Media Players
  * [Sony TV](https://goo.gl/C2V2Rr)
  * [Sony Playstation PS4 Pro](https://goo.gl/sjZd4q)
  * [Kodi - App on TV](https://kodi.tv)

### To Buy
* Sensors - Consider getting Z-Wave USB stick and use Z-Wave sensors
  * Door Sensor (with motion sensor preferably)
  * Motion Sensor (x2)
* Switches
  * [TP-Link HS100 Smart Switch](https://goo.gl/WL54Ae)

## Presence
Tracking with:
* Owntracks 
* ping - Not as reliable, logging to asses validaity

I use an Automation which sets a Boolean to 'Home' or 'Away' according to the presence detection methods I'm using - This allows me to add or delete presence detection methods without effecting other Automations

## Automations
* Lights
  * Turn on the Stairs light between 00:00 and 05:00 (weekdays)
  * Turn on the the entrance light with motion detection between 05:30 and 12:00 (weekdays)
  * Turn on the Bedroom Lamp for Ruby as a natural Alarm (weekdays)
  * Turn on the Stairs light between 00:00 and 12:00 (weekends)
  * Turn on the Bedroom Lamp and Entrance light after 12:00 (Below a specific lught level)
  * Turn off the Entrance and Stairs lights 2 min after motin has been detected
  * Turn off the Bedroom Lamp if the TV is on
* Notifications
  * Notify when HA Update is available
  * Notify if SSL certificate goes below 21 days
  * Reminder to take Electricty and Gas Meter readings every Monday when I arrive home
* Alarms
  * Alarm of motiion detected when I'm not home (disable for 10 mins after first detection)
* Location
  * Automate Boolean to set to 'Home' or 'Away' accordingly
* Generic
  * Change TV input if the PS4 is On or OFF

## ToDo
* Lighting
  * With added motion sensors turn on/off lights according to which motion sensor has been activated
* Automations
  * Use Input Booleans/Scripts as much as possible - this means that when I change a bulb/method of detection/etc I don't need to change the automation
  * Add bayesian binary sensor to be able to improve automations - (similar to if TV is off and after 21:00 probability of being in bed is high)
  * Change lamp colour depending on train status - Look at [Set Lamp colour depending on train status](https://goo.gl/hdmLe8)
  * Look at [CCOSTAN config](https://goo.gl/jxdfkm) for inspiration
* Sensors
  * Look at reducing the number of scan intervals needed for each sensor
  * Add transport from Euston to Birmingham International and vice versa
  * Add Battery status of motion sensor by creating a [RESTful sensor](https://goo.gl/cmipSo)
* Alarm
  * Add MQTT alarm with IR and camera using Pi Zero W, Touch Screen, Pi Camera and 3D printed case
  * Add scripts/automations to take still photos and send to phone as email/notifications
* Customize HA
  * Change icon colours when state changes
  * Look at implementing floorplan
* Voice Integration
  * Add AWS Polly Voice service for Echo Dots - [Reference](https://goo.gl/QaVZWA)
* Look at implementing AWS RDS to log history (mainly as a learning exercise) 

## Lessons Learnt
* As much as I love the Philips Hue Bulbs/Motion Sensor and app, should have gone with the Z-wave option as the Hue Zigbee protocol seems to be too restrictive

