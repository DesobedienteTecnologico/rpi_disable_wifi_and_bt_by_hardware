# Disabling WiFI/Bluetooth by hardware [ Raspberry Pi Zero W and Zero 2 W ]

# Tranlations
 - <a href="https://github.com/DesobedienteTecnologico/rpi_disable_wifi_and_bt_by_hardware/blob/main/README_es.md">Español</a>

### Index:
 1. Intro.
 1. CYW/BCM43438 schematics.
 1. X-ray images and WLBGA ball map (colored).
 1. Images showing what to remove and extra.
 1. Check by terminal if WiFi and Bluetooth are disconnected.
 ---
 # Intro:

One of the biggest problems are that Raspberry Pi do not show the schematics of the wireless. 
See this example: https://datasheets.raspberrypi.com/rpizero/raspberry-pi-zero-w-reduced-schematics.pdf

Thanks that we got access to a X-ray picture of the wireless chip, I tried to figure out some of the circuits. Not easy because that PCB is multilayer. So I just figured out some of them.

The best news are that RPi Zero w and RPi Zero 2 W wireless chip still in the same position, is not rotated and in both boards we should remove exactly the same SMD component. Cool!, isn't it? 🙂

I didn't end up removing <a href="https://en.wikipedia.org/wiki/IC_power-supply_pin">VDD</a> becasuse I can't see well the all layers and to me seems like <a href="https://en.wikipedia.org/wiki/IC_power-supply_pin">VDD</a> comes from another PCB layer under the chip.

---
# CYW/BCM43438 schematics:

#### Basic schematics showing were we are going to get rid of the SMD inductor.
![image.png](images/1.png)

Documentation source: (https://www.cypress.com/file/298076/download)

---
# X-ray images and WLBGA ball map (colored):

### 🟠 Orange big dot made as position reference.


#### Here we have the X-ray image and normal one to let you know the actual position. 

![](images/2.png)

X-ray image by **@Vilas1979**

![](images/3.png)

---
# Images showing what to remove and extra:

### Image showing what to remove to disable WiFi/Bluetooth by removing the inductor that goes to the pin **SR_VLX**:
Information about **SR_VLX**:
![](images/4.png)

VDD and GND still connected into the board but chip is not able to work without the inductor. But don't worry:

💡 **As a simile**: Having a car with 1 of 3 <a href="https://en.wikipedia.org/wiki/Anti-lock_braking_system">ABS/brakes</a> cable broken. The engine will start, but the ECU will detect that the <a href="https://en.wikipedia.org/wiki/Anti-lock_braking_system">ABS</a> is not reachable. So is impossible to get connected to it, transmit any data and use that component.

![](images/5.png)

### EXTRA: If you got the case that you would like just to remove the WiFi, just remove this component:

![](images/6.png)


### Random desoldering iron tutorial for SMD:
- [Desoldering online video from DuckDuckGo](https://duckduckgo.com/video_frame?url=https%3A%2F%2Fwww.youtube-nocookie.com%2Fembed%2F7jQXYmZKvYU%3Fwmode%3Dtransparent%26iv_load_policy%3D3%26autoplay%3D1%26html5%3D1%26showinfo%3D0%26rel%3D0%26modestbranding%3D1%26playsinline%3D0%26theme%3Dlight)

### Text tutorial just using desoldering iron:

- Get soldering iron quite warm. Put the soldering iron on top of each extremes (first one, and then the other) of the SMD and push a bit to one side.

---

# Check by terminal if WiFi and Bluetooth are disconnected.

#### WiFi
Once you boot the system, open Terminal and type:
 - `ip addr`

If there is not **wlan0**, WiFi is disabled by hardware.

#### Bluetooth
Open Terminal and type:
 - `bluetoothctl`

If bluetoothctl do not open or seems to be frozen, is good signal... But if open type:
 - `scan on`

If you can see values (Probably not), write me back.

Enjoy!

---

###### License: **CC BY 4.0**
