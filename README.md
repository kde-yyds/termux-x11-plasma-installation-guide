# termux-x11-plasma-installation-guide
termux-x11运行KDE Plasma教程
# 安装
## termux 
下载 https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk 
## termux-x11
下载https://github.com/kde-yyds/termux-x11-plasma-installation-guide/raw/master/termux-x11/termux-x11.apk 并安装
打开termux
apt install x11-repo wget -y  
wget https://github.com/kde-yyds/termux-x11-plasma-installation-guide/raw/master/termux-x11/termux-x11.deb  
apt install ./termux-x11.deb  
## proot容器
建议用tmoe搭建
## ubuntu 21.10 impish
### why
kwin 5.22.8之后xrender后端被删除，只能使用glx渲染后端，但termux-x11不支持glx,所以只能用xrender
ubuntu impish的kwin是5.22.5
### 安装
#### 安装ubuntu focal
#### 升级到ubuntu impish
` echo deb http://old-releases.ubuntu.com/ubuntu impish main universe multiverse restricted > /etc/apt/sources.list.d/1.list  
echo deb http://old-releases.ubuntu.com/ubuntu impish-updates main universe multiverse restricted > /etc/apt/sources.list.d/2/list    
apt update    
apt upgrade  `
#### 安装plasma
`apt install kde-full dbus-x11`
#### 共享tmp
# 运行
## termux-x11
`termux-x11 :1 -dpi 200&`
## plasma
进入容器
`export DISPLAY=:1`  

`startplasma-x11`


