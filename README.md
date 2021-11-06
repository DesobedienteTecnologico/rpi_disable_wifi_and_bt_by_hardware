# Disabling WiFI/Bluetooth by hardware [ Raspberry Pi Zero W and Zero 2 W ]

### Index:
 1. Intro.
 1. CYW/BCM43438 schematics.
 1. X-ray images and WLBGA ball map (colored).
 1. Images showing what to remove and extra.
 ---

One of the biggest problems are that Raspberry Pi do not show the schematics of the wireless. 
See this example: https://datasheets.raspberrypi.com/rpizero/raspberry-pi-zero-w-reduced-schematics.pdf

Thanks that we got access to a X-ray picture of the wireless chip, I tried to figure out some of the circuits. Not easy because that PCB is multilayer. So I just figured out some of them.

The best news are that RPi Zero w and RPi Zero 2 W wireless chip still in the same position, is not rotated and in both boards we should remove exactly the same SMD component. Cool!, isn't it? :)

---

#### Basic schematics showing were we are going to get rid of the SMD inductor.
![image.png](images/1.png)

Documentation source: (https://www.cypress.com/file/298076/download)

---
### 🟠 Orange big dot made as position reference.


#### Here we have the X-ray image and normal one to let you know the actual position. 

![](images/2.png)

X-ray image by **@Vilas1979**

![](images/3.png)

---

### Image showing what to remove to disable WiFi/Bluetooth by removing the inductor that goes to the pin **SR_VLX**:

![](images/5.png)

### If you got the case that you would like just to remove the WiFi, just remove this component:

![](images/6.png)


### Desoldering iron tutorial:
- [Desoldering online video from DuckDuckGo](https://duckduckgo.com/video_frame?url=https%3A%2F%2Fwww.youtube-nocookie.com%2Fembed%2F7jQXYmZKvYU%3Fwmode%3Dtransparent%26iv_load_policy%3D3%26autoplay%3D1%26html5%3D1%26showinfo%3D0%26rel%3D0%26modestbranding%3D1%26playsinline%3D0%26theme%3Dlight)

License: DesobedienteTecnologico **CC BY 4.0**


```python

```
