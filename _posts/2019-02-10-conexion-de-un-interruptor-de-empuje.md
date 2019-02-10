---
title: Conexión de un interruptor de empuje
---

https://www.youtube.com/watch?v=3TDJ4FmtGgk

Conecte un interruptor a un pin GPIO y use la biblioteca RPi.GPIO en su programa Python para detectar la presión del botón.

**Diagrama de la conexión:**

![Imgur](https://i.imgur.com/P4ecbKs.png)

**Contenido del archivo switch.py**

```
import RPi.GPIO as GPIO
import time

GPIO.setmode(GPIO.BCM)

GPIO.setup(18, GPIO.IN, pull_up_down=GPIO.PUD_UP)

while True:
    input_state = GPIO.input(18)
    if input_state == False:
        print('Button Pressed')
        time.sleep(0.2)

```

**Ejecuta tu script:**

```
$ sudo python switch.py
```