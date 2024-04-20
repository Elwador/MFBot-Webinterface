# MFBot-Webinterface

Currently waiting for full release of mfbot v6.0

A simple webinterface for the [Shakes & Fidget bot](https://hub.docker.com/r/mfbot/mfbot)! 

The webinterface uses the set environment variable to connect to your instance of the mfbot. 

Currently there is only the dev tag because i am still working on the interface and it is still missing a few things.

## Usage

To use the interface with the bot it is necesarry to adjust some settings.

1. Start the MFBot docker in the host network

Add this to the docker start command:
```
--network host
```
2. The MFBot has to have the "Remote access" enabled in the "Global Settings". Also the Port has to be set to something that isn't used by something else and the ip has to be changed to host ip. (to check if everything is working simply go to "http://[IP]:[PORT]")

3. After configuring the MFBot it is necesarry to tell the webinterface  where to find the bot. That is done with the environment variable 'API_HOST'. It can be added to the docker run command in the following way.

IP to the MFBot:
```
-e 'API_HOST'='http://XXX.XXX.XXX.XXX:XXXX/'
```

4. Now only the port for the Webinterface has to be set '8888' is just a place holder you can change it to whatever you want or leave it at '8888'.

Port:
```
-p '8888:80/tcp'
```

## Unraid
Since the image is only on docker hub unraid doesn't set the WebUi url and the icon.
To change that you have to go to the docker and under edit in the advanced view set the following fields.

Icon URL: 
```
https://raw.githubusercontent.com/Elwador/MFBot-Webinterface/main/images/icon_docker.png
```

WebUI:
```
http://[IP]:[PORT:80]/
```

## Issues
If you run int any problems feel free to write a ticket at [Issues](https://github.com/Elwador/MFBot-Webinterface/issues)
