# Deshabilitar WiFi/Bluetooth por hardware [ Raspberry Pi Zero W and Zero 2 W ]

### Index:
 1. Introducción.
 1. Esquema de CYW/BCM43438.
 1. Imágen en rayos-x y mapa de los pines del chip (en color).
 1. Imágen enseñando lo que hay que quitar de la placa y un extra.
 1. Comprobar por Terminal si el WiFi o Bluetooth está desconectado.
 ---
 # Introducción:

Uno de los mayores problemas que hay con Raspberry Pi, es que no muestran los esquemas del chip encargado del WiFi y Bluetooth. Míra este ejemplo:: https://datasheets.raspberrypi.com/rpizero/raspberry-pi-zero-w-reduced-schematics.pdf

Gracias a que tuve acceso a una imágen rayos-X del chip encargado del WiFi/Bluetoth, he intentadó adivinar como están las pistas del circuito. Nada facil ya que la placa PCB tiene mas de una capa con pistas. Por lo tanto solo he podido adivinar algunas de ellas.

La mejor noticia es que la RPi Zero W y la RPi Zero 2 W utilizan el mismo chip y en la misma posición. No está ni siquiera rotada, lo que significa que el procedimiento será el mismo para los placas! :). 
  
No terminé eliminando la conexión de <a href="https://ejemplos.net/que-significa-vcc/">VDD</a> por que no puedo ver bien todas las capas de la PCB y para mí que <a href="https://ejemplos.net/que-significa-vcc/">VDD</a> viene de una de las capas inferiores bajo del chip.

---
# Esquema de CYW/BCM43438:

#### Esquema básico mostrando donde vamos a tener que quitar el inductor SMD.
![image.png](images/1.png)

Fuente de la Documentation: (https://www.cypress.com/file/298076/download)

---
# Imágen en rayos-x y mapa de los pines del chip (en color)

### 🟠 Círculo naranja grande creado para hacer de referencia a la posición del chip.

#### Aquí tenemos la imagen de rayos-X y una imagen normal para mostrarte la posición actual.

![](images/2.png)

Imagen de rayos-X por **@Vilas1979**

![](images/3.png)

---
# Imágen enseñando lo que hay que quitar de la placa y un extra 

### Imagen mostrando lo que hay que eliminar para deshabilitar WiFi/Buetooth. Quitando el inductor que hace referencia al pin **SR_VLX**:

Información sobre **SR_VLX**:
![](images/4.png)

VDD y GND siguen estando conectado a la placa, pero el chip no será capaz de trabajar faltando el inductor. Pero no te preocupes.

💡 **Pequeño ejemplo de similitud**:
Teniendo un coche con 1 de 3 cables del <a href="https://es.wikipedia.org/wiki/Sistema_antibloqueo_de_ruedas">ABS</a> roto. El coche arrancará, pero la centralíta detectará que hay un error ya que no se puede comunicar con el ABS. Entoncés al ser imposible comunicarse con el <a href="https://es.wikipedia.org/wiki/Sistema_antibloqueo_de_ruedas">ABS</a> no funcionará incluso estando en un momento crítico que sea importante utilizarlo.

![](images/5.png)

### EXTRA: Si solamente quieres deshabilitar el WiFi, simplemente quita este componente:

![](images/6.png)

### Tutorial aleatorio que conseguí para desoldar componentes SMD:
- [Vídeo desde DuckDuckGo](https://duckduckgo.com/video_frame?url=https%3A%2F%2Fwww.youtube-nocookie.com%2Fembed%2F7jQXYmZKvYU%3Fwmode%3Dtransparent%26iv_load_policy%3D3%26autoplay%3D1%26html5%3D1%26showinfo%3D0%26rel%3D0%26modestbranding%3D1%26playsinline%3D0%26theme%3Dlight)

### Tutorial escrito para desoldar con un soldador de estaño:

- Get soldering iron quite warm. Put the soldering iron on top of each extremes (first one, and then the other) of the SMD and push a bit to one side.

- Tén el soldador bastante caliente. Pon el soldador en un extremo del componente SMD, luego en el otro. Así un par de veces y has una leve presión hacia un lado para poder sacarlo.

---
# Comprobar por Terminal si el WiFi o Bluetooth está desconectado.

#### WiFi

Cuando hayas iniciado el sistema, conéctate por el Terminal y escribe:
 - `ip addr`

Si no ves wlan0, el WiFi estára deshabilidado por hardware.

#### Bluetooth
Abre un terminal y escribe:
 - `bluetoothctl`

Si bluetoothctl no abre y parece estár congelado, es buena señal... Pero si se abre, escribe:
 - `scan on`

Si puedes ver valores (Posiblemente no), escríbeme.

A disfrutar!

---

###### Licencia: **CC BY 4.0**
