# Common-and-Rare-VM-Ware-and-Linux-issues
## Fix VMWare Screen not reacting to mouse clicks in certain areas of the Screen after a while of working.  
Use following linux command to find the DnD window ID  

```
└─$ xwininfo -tree -root | grep VBox
     0xa00001 "VBoxClientWndDnD": ()  800x600+0+0  +0+0
     0x400001 "main": ("main" "VBoxShCl")  1x1+0+0  +0+0
```

In this case it is 0xa00001. You can see the dimensions of it and where it is placed (usually that's the part of the screen that is not reacting anymore)  

Use following linux command to change the height and width of that window to 1px  
```
└─$ xdotool windowsize 0xa00001 1 1 
```
## Fix Linux screen being glitched / Linux windows not having buttons / Linux desktop not having icons / Linux not reacting outside of terminal / Linux not having Workspaces / Linux glitched Workspaces
Just open a terminal and enter
```
└─$ xfwm4
```
It will restart the rendering services
