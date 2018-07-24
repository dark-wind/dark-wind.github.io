---
title: "orangePi 摄像头调用"
categories: linux
tags: orangePi camera
toc: true
toc_label: 目录
---
## 摄像头识别
玩狼人杀的时候从老板哪里15块买的山寨摄像头
兼容性居然还蛮好
运行命令
```
lsusb
```
对比插上前后的变化
```
Bus 008 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 005 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 007 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 004 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 006 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 003 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 002 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
```
```
Bus 008 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 005 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 007 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 004 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 006 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 003 Device 003: ID 1908:2311 GEMBIRD
Bus 003 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 002 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
```
很容易发现，多了个GEMBIRD
就它了

## MJPEG-Streamer安装
网上资料大都过期了，还是官网靠谱

1. [安装指南](https://github.com/cncjs/cncjs/wiki/Setup-Guide:-Raspberry-Pi-%7C-MJPEG-Streamer-Install-&-Setup-&-FFMpeg-Recording)
2. 安装命令-可能会失效，以安装指南为准

```
# Update & Install Tools
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get install build-essential libjpeg8-dev imagemagick libv4l-dev cmake -y

# Clone Repo in /tmp
cd /tmp
git clone https://github.com/jacksonliam/mjpg-streamer.git
cd mjpg-streamer/mjpg-streamer-experimental

# Make
make
sudo make install

# Run
/usr/local/bin/mjpg_streamer -i "input_uvc.so -r 1280x720 -d /dev/video0 -f 30 -q 80" -o "output_http.so -p 8080 -w /usr/local/share/mjpg-streamer/www"
```
## 访问

```
http://localhost:8080/stream.html
```
## 运行失败
运行失败可能是忘了插摄像头o(╯□╰)o

依赖安装失败
```
darkwind@orangepizero:/sys/bus/usb/devices$ sudo apt-get install build-essential libjpeg8-dev imagemagick libv4l-dev cmake -y
Reading package lists... Done
Building dependency tree
Reading state information... Done
Package libjpeg8-dev is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source
However the following packages replace it:
  libjpeg62-turbo-dev

E: Package 'libjpeg8-dev' has no installation candidate
```
替换依赖
```
sudo apt-get install build-essential libjpeg62-turbo-dev imagemagick libv4l-dev cmake -y
```
启动失败
```
darkwind@orangepizero:~/temp/mjpg-streamer/mjpg-streamer-experimental$ sudo ./mjpg_streamer -i "./input_uvc.so -f 10 -r 320x240 -d /dev/video0 -y -n" -o "./output_http.so -w ./www -p 8080"
MJPG Streamer Version: git rev: f387bb44e6c087271b763b27da998bf2e06c4f5d
 i: Using V4L2 device.: (null)
 i: Desired Resolution: 320 x 240
 i: Frames Per Second.: 10
 i: Format............: YUYV
 i: JPEG Quality......: 80
 i: TV-Norm...........: DEFAULT
 i: init_VideoIn failed
```
可以加入参数
```
-yuv
mjpg_streamer -i "input_uvc.so -d /dev/video0 -r 640x480 -f 20 -yuv"  -o "output_http.so -p 8082 -w /www/camwww"
```
O(∩_∩)O~其实我重启它自己就好了，机智的自己变格式
```
MJPG Streamer Version: git rev: f387bb44e6c087271b763b27da998bf2e06c4f5d
 i: Using V4L2 device.: /dev/video0
 i: Desired Resolution: 320 x 240
 i: Frames Per Second.: 30
 i: Format............: JPEG
 i: TV-Norm...........: DEFAULT
 i: Could not obtain the requested pixelformat: MJPG , driver gave us: YUYV
    ... will try to handle this by checking against supported formats.
    ... Falling back to YUV mode (consider using -yuv option). Note that this requires much more CPU power
UVCIOC_CTRL_ADD - Error at Pan (relative): Inappropriate ioctl for device (25)
UVCIOC_CTRL_ADD - Error at Tilt (relative): Inappropriate ioctl for device (25)
UVCIOC_CTRL_ADD - Error at Pan Reset: Inappropriate ioctl for device (25)
UVCIOC_CTRL_ADD - Error at Tilt Reset: Inappropriate ioctl for device (25)
UVCIOC_CTRL_ADD - Error at Pan/tilt Reset: Inappropriate ioctl for device (25)
UVCIOC_CTRL_ADD - Error at Focus (absolute): Inappropriate ioctl for device (25)
UVCIOC_CTRL_MAP - Error at Pan (relative): Inappropriate ioctl for device (25)
UVCIOC_CTRL_MAP - Error at Tilt (relative): Inappropriate ioctl for device (25)
UVCIOC_CTRL_MAP - Error at Pan Reset: Inappropriate ioctl for device (25)
UVCIOC_CTRL_MAP - Error at Tilt Reset: Inappropriate ioctl for device (25)
UVCIOC_CTRL_MAP - Error at Pan/tilt Reset: Inappropriate ioctl for device (25)
UVCIOC_CTRL_MAP - Error at Focus (absolute): Inappropriate ioctl for device (25)
UVCIOC_CTRL_MAP - Error at LED1 Mode: Inappropriate ioctl for device (25)
UVCIOC_CTRL_MAP - Error at LED1 Frequency: Inappropriate ioctl for device (25)
UVCIOC_CTRL_MAP - Error at Disable video processing: Inappropriate ioctl for device (25)
UVCIOC_CTRL_MAP - Error at Raw bits per pixel: Inappropriate ioctl for device (25)
 o: www-folder-path......: /usr/local/share/mjpg-streamer/www/
 o: HTTP TCP port........: 8080
 o: HTTP Listen Address..: (null)
 o: username:password....: disabled
 o: commands.............: enabled
```

## 开机自启

```
nano /home/pi/mjpg-streamer.sh
```
写入

```
#!/bin/bash
# chmod +x mjpg-streamer.sh
# Crontab: @reboot /home/pi/mjpg-streamer/mjpg-streamer.sh start
# Crontab: @reboot /home/pi/mjpg-streamer/mjpg-streamer-experimental/mjpg-streamer.sh start

MJPG_STREAMER_BIN="/usr/local/bin/mjpg_streamer"  # "$(dirname $0)/mjpg_streamer"
MJPG_STREAMER_WWW="/usr/local/share/mjpg-streamer/www"
MJPG_STREAMER_LOG_FILE="${0%.*}.log"  # "$(dirname $0)/mjpg-streamer.log"
RUNNING_CHECK_INTERVAL="2" # how often to check to make sure the server is running (in seconds)
HANGING_CHECK_INTERVAL="3" # how often to check to make sure the server is not hanging (in seconds)

VIDEO_DEV="/dev/video0"
FRAME_RATE="5"
QUALITY="80"
RESOLUTION="1280x720"  # 160x120 176x144 320x240 352x288 424x240 432x240 640x360 640x480 800x448 800x600 960x544 1280x720 1920x1080 (QVGA, VGA, SVGA, WXGA)   #  lsusb -s 001:006 -v | egrep "Width|Height" # https://www.textfixer.com/tools/alphabetical-order.php  # v4l2-ctl --list-formats-ext  # Show Supported Video Formates
PORT="8081"
YUV="yes"

################INPUT_OPTIONS="-r ${RESOLUTION} -d ${VIDEO_DEV} -f ${FRAME_RATE} -q ${QUALITY} -pl 60hz"
INPUT_OPTIONS="-r ${RESOLUTION} -d ${VIDEO_DEV} -q ${QUALITY} -pl 60hz --every_frame 2"  # Limit Framerate with  "--every_frame ", ( mjpg_streamer --input "input_uvc.so --help" )


if [ "${YUV}" == "true" ]; then
	INPUT_OPTIONS+=" -y"
fi

OUTPUT_OPTIONS="-p ${PORT} -w ${MJPG_STREAMER_WWW}"

# ==========================================================
function running() {
    if ps aux | grep ${MJPG_STREAMER_BIN} | grep ${VIDEO_DEV} >/dev/null 2>&1; then
        return 0

    else
        return 1

    fi
}

function start() {
    if running; then
        echo "[$VIDEO_DEV] already started"
        return 1
    fi

    export LD_LIBRARY_PATH="$(dirname $MJPG_STREAMER_BIN):."

	echo "Starting: [$VIDEO_DEV] ${MJPG_STREAMER_BIN} -i \"input_uvc.so ${INPUT_OPTIONS}\" -o \"output_http.so ${OUTPUT_OPTIONS}\""
    ${MJPG_STREAMER_BIN} -i "input_uvc.so ${INPUT_OPTIONS}" -o "output_http.so ${OUTPUT_OPTIONS}" >> ${MJPG_STREAMER_LOG_FILE} 2>&1 &

    sleep 1

    if running; then
        if [ "$1" != "nocheck" ]; then
            check_running & > /dev/null 2>&1 # start the running checking task
            check_hanging & > /dev/null 2>&1 # start the hanging checking task
        fi

        echo "[$VIDEO_DEV] started"
        return 0

    else
        echo "[$VIDEO_DEV] failed to start"
        return 1

    fi
}

function stop() {
    if ! running; then
        echo "[$VIDEO_DEV] not running"
        return 1
    fi

    own_pid=$$

    if [ "$1" != "nocheck" ]; then
        # stop the script running check task
        ps aux | grep $0 | grep start | tr -s ' ' | cut -d ' ' -f 2 | grep -v ${own_pid} | xargs -r kill
        sleep 0.5
    fi

    # stop the server
    ps aux | grep ${MJPG_STREAMER_BIN} | grep ${VIDEO_DEV} | tr -s ' ' | cut -d ' ' -f 2 | grep -v ${own_pid} | xargs -r kill

    echo "[$VIDEO_DEV] stopped"
    return 0
}

function check_running() {
    echo "[$VIDEO_DEV] starting running check task" >> ${MJPG_STREAMER_LOG_FILE}

    while true; do
        sleep ${RUNNING_CHECK_INTERVAL}

        if ! running; then
            echo "[$VIDEO_DEV] server stopped, starting" >> ${MJPG_STREAMER_LOG_FILE}
            start nocheck
        fi
    done
}

function check_hanging() {
    echo "[$VIDEO_DEV] starting hanging check task" >> ${MJPG_STREAMER_LOG_FILE}

    while true; do
        sleep ${HANGING_CHECK_INTERVAL}

        # treat the "error grabbing frames" case
        if tail -n2 ${MJPG_STREAMER_LOG_FILE} | grep -i "error grabbing frames" > /dev/null; then
            echo "[$VIDEO_DEV] server is hanging, killing" >> ${MJPG_STREAMER_LOG_FILE}
            stop nocheck
        fi
    done
}

function help() {
    echo "Usage: $0 [start|stop|restart|status]"
    return 0
}

if [ "$1" == "start" ]; then
    start && exit 0 || exit -1

elif [ "$1" == "stop" ]; then
    stop && exit 0 || exit -1

elif [ "$1" == "restart" ]; then
    stop && sleep 1
    start && exit 0 || exit -1

elif [ "$1" == "status" ]; then
    if running; then
        echo "[$VIDEO_DEV] running"
        exit 0

    else
        echo "[$VIDEO_DEV] stopped"
        exit 1

    fi

else
    help

fi
```

增加自启队列

```
# Make Executable
chmod +x /home/pi/mjpg-streamer.sh

# Open Cron Job
crontab -e

# Add line
@reboot /home/pi/mjpg-streamer.sh start
```

## 内网穿透
因为有一台阿里云做跳板，反向代理即可
### 创建本机秘钥

```
cd ~/.ssh/
ssh-keygen
```
### 公网服务器写入公钥

```
ssh-copy-id user@server
```
### 端口转发

```
sudo nano sshr.sh
```

在exit 0 前写入

```
nohup ssh -NR 0.0.0.0:30522:127.0.0.1:22 username@serverIP > /dev/null 2>&1 &
nohup ssh -NR 0.0.0.0:30580:127.0.0.1:8080 username@serverIP > /dev/null 2>&1 &
```

22端口用于远程ssh登录

8080端口是默认的MJPEG-Streamer页面访问端口

增加执行权限
```
sudo chmod +x sshr.sh
```

### 增加心跳

```
nano /etc/ssh/ssh_config
```
加入
```
TCPKeepAlive yes
ServerAliveInterval 300
```

## 参考资料

[Linux中显示系统中USB信息的lsusb命令](https://linux.cn/article-2448-1.html)

[Setup Guide:MJPEG Streamer Install & Setup & FFMpeg Recording](https://github.com/cncjs/cncjs/wiki/Setup-Guide:-Raspberry-Pi-%7C-MJPEG-Streamer-Install-&-Setup-&-FFMpeg-Recording)

[【手把手教你树莓派3 （六）】使用 motion 和 mjpg 做视频监控器](https://blog.csdn.net/u010900754/article/details/53097626)

[【派】0004-摄像头监控](https://www.jianshu.com/p/f8ebf921daf2)

[树莓派上MJPG-streamer安装手顺](https://www.jianshu.com/p/069c61315e8a)

[ssh-copy-id命令](http://man.linuxde.net/ssh-copy-id)