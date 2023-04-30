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
4. Schedule it for 1 your execution of the bach (background) robot
```bash
# Schedule SeedRobot.sh bash robot to run every hour by CRONTAB
0 * * * * ~/bin/SpeedRobot.sh
```
---
The next step is to wrap it up for the everyday user's installation and usage!<br>
Extend to Facebook, Instagram, LinkedIn, and other social media...<br>
Computer Science and Engineering students can create projects from here to rebuild them in Java, Python, R, etc...<br>
Data Science students can create a more systematic analysis of Internet traffic and operators' (ISP) quality and consistency
