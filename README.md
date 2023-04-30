# speed-robot
Internet speed Twitter robot (SpeedRobot.sh)

As almost everybody works from home, Internet availability and speed are important.<br>
When we have issues, the operators (telecom companies) try to attend to us with robots! (clearly, they don't care!)

So we can create our own robots too!! In response!!

Here we get together some tech to create a speed test robot quickly and Twitter the report in a schedule (such as hourly basis) to keep operators informed!

Tools:

## Speedtest

Speedtest by Ookla is a good option https://www.speedtest.net, we can download and install a local command line version:
https://www.speedtest.net/apps/cli

Graphical report example:<br>
![](https://www.speedtest.net/result/14675293137.png)

Command line report example:
```bash
   Speedtest by Ookla

      Server: FORÇA E AÇÃO TELECOM - Diadema (id: 31133)
         ISP: Claro NET
Idle Latency:    17.47 ms   (jitter: 2.74ms, low: 13.88ms, high: 20.34ms)
    Download:    30.88 Mbps (data used: 52.3 MB)                                                   
                374.07 ms   (jitter: 78.71ms, low: 47.04ms, high: 1358.62ms)
      Upload:    34.07 Mbps (data used: 18.9 MB)                                                   
                 71.35 ms   (jitter: 21.05ms, low: 26.83ms, high: 341.94ms)
 Packet Loss:     0.0%
  Result URL: https://www.speedtest.net/result/c/3ed0f928-6340-45bd-9795-438565839bdb
```

Command line to get result in JSON:

```bash
$ speedtest -f json-pretty

{
    "type": "log",
    "timestamp": "2023-04-30T05:00:23Z",
    "message": "Error: [0] Timeout occurred in connect.",
    "level": "error"
}
{
    "type": "result",
    "timestamp": "2023-04-30T05:00:46Z",
    "ping": {
        "jitter": 3.677,
        "latency": 19.566,
        "low": 19.167,
        "high": 26.570
    },
    "download": {
        "bandwidth": 43595912,
        "bytes": 384385628,
        "elapsed": 8904,
        "latency": {
            "iqm": 361.014,
            "low": 18.950,
            "high": 657.445,
            "jitter": 75.102
        }
    },
    "upload": {
        "bandwidth": 1990503,
        "bytes": 26262348,
        "elapsed": 12912,
        "latency": {
            "iqm": 22.246,
            "low": 14.501,
            "high": 34.657,
            "jitter": 3.945
        }
    },
    "packetLoss": 0,
    "isp": "Claro NET",
    "interface": {
        "internalIp": "0000:000:00:0000:0000:0000:0000:0000",
        "name": "wlp2s0",
        "macAddr": "00:00:00:00:00:00",
        "isVpn": false,
        "externalIp": "0000:000:00:0000:0000:0000:0000:0000"
    },
    "server": {
        "id": 43094,
        "host": "speedtest.nossanetfibra.com.br",
        "port": 8080,
        "name": "Nossanet Fibra",
        "location": "São Paulo",
        "country": "Brazil",
        "ip": "2804:4e50:beba:cafe::2"
    },
    "result": {
        "id": "dde47777-9e59-4ad6-af95-81b3647c5e16",
        "url": "https://www.speedtest.net/result/c/dde47777-9e59-4ad6-af95-81b3647c5e16",
        "persisted": true
    }
}

```

The result in PNG:<br>
https://www.speedtest.net/result/c/3ed0f928-6340-45bd-9795-438565839bdb.png

## Twitter API

Connect and send Twitter messages by WEB API:<br>
https://developer.twitter.com

## Bash Send Tweet

A project as a reference to send messages by Bash:<br>
https://github.com/agubelu/bash-send-tweet

## How to create images from text messages...

ImageMagic command line tool to convert text to images and attach to Twitter message:<br>
https://imagemagick.org/index.php

## Steps:

Robot (bash script) step-by-step:

1. Run speedtest script from Ookla and save the result in a text temporary file (or pipe it)
2. Convert the text with Internet speed results to an image with ImageMagic
3. Send a Twitter message sharing the speed and reference your operator too, attach the image
4. Schedule it for 1 hour execution of the bach (background) robot
```bash
# Schedule SeedRobot.sh bash robot to run every hour by CRONTAB
0 * * * * ~/bin/SpeedRobot.sh
```
---
## Next steps:

- Wrap it up for the everyday user's installation and usage!<br>
- Extent to Facebook, Instagram, LinkedIn, and other social media...<br>
- Computer Science and Engineering students can create projects from here to rebuild them in Java, Python, R, etc...<br>
- Data Science students can create a more systematic analysis of Internet traffic and operators' (ISP) quality and consistency
- Get more devs involve
- Have it published at the press
