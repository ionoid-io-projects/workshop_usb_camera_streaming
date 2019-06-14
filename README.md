# Video streaming using ffmpeg

## Installation
Install ffmpeg on Raspberry Pi and execute it.

```
sudo apt-get install ffmpeg 
```

## Configure ffmpeg server

Copy file "ffserver_workshop.conf" to your raspberry pi home directory /home/pi/

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
To get the device ip execute on your raspberry pi 
```
ip a
```

## access to your camera stream from your desktop

On your computer use the browser to connect at *http://rpi_device_ip:8080/camera.mjpeg*

Happy streaming