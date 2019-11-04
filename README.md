# Video streaming using ffmpeg

## 1- Power your raspberry

You can achive it with connecting it to your pc trought the Micro USB Port of the raspberry pi

![power](1-min.jpg)

## 2- Connect to your raspberry pi
Using putty if you're on windows, Ssh if you're on a linux based os
Follow the following instruction if you dont know how to connect to raspberry pi
[Connect to Raspberry Pi using Putty](https://github.com/ionoid-io-projects/workshop/blob/master/doc/od-iot-raspbian-rpi-zero-windows.md#5-first-boot)

## Installation
Install ffmpeg on Raspberry Pi and execute it.

```
sudo apt-get install ffmpeg 
```

## Configure ffmpeg server

Download the file "ffserver_workshop.conf" to your home directory using
the following command:

```
curl -O https://raw.githubusercontent.com/ionoid-io-projects/workshop_usb_camera_streaming/master/ffserver_workshop.conf
```

## Launch streaming server

Launch ffserver, execute the following command inside your raspberry pi
```
ffserver -f /home/pi/ffserver_workshop.conf &
```

Execute ffmpeg with the following parameters.

```
ffmpeg -f v4l2 -s 640x480 -r 15 -i /dev/video0 http://rpi_device_ip:8080/camera.ffm
```
Replace 'rpi_device_ip' with the ip of your raspberry pi, 

## How to stop the program
To quit or stop the program click on **Ctrl+C**

## access to your camera stream from your desktop

On your computer use the browser to connect at *http://rpi_device_ip:8080/camera.mjpeg*

Happy streaming
