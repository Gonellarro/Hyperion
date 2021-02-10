![ambilight](imgs/ambilight.jpg)

# Instalación de Hyperion para ambilight

## Fase 1.  Instalación en el Wemos D1 Mini

### IDE

a) Ardunio IDE

### Librería de placas

a) esp8266 2.4.1 http://arduino.esp8266.com/stable/package_esp8266com_index.json

### Librerías

​	a) ArduinoThread 2.1.1

​	b) ArduinoJSON 5.12.0

​	c) LinkedList 1.2.3

​	d) FastLED 3.1.6

​	e) Logging https://github.com/SciLor/Arduino-logging-library - install manually: Download zip 	from github and install via Arduino IDE, Sketch -> Include Library -> Add .ZIP Library

### Instalación

#### Configuración de la placa

1. Vaya a la carpeta `HyperionRGB`y cree una copia del fichero `ConfigStatic.h.example`. Eliminar el sufijo `.example`
2. Configure el fichero  `ConfigStatic.h` según sus necesidades:
   - Seleccione su tipo de chip LED. Todos los LED de las bibliotecas [FastLed](https://github.com/FastLED/FastLED) son compatibles
   - Configure los pines LED usados. También puede cambiar el orden de los pines. El pedido de NodeMCU no funciona a veces, pruebe también el `` RAW_PIN_ORDER``
   - Definir el número de LED usados
   - Defina uno de los modos estándar que están activos cuando su luz está inactiva. Elija uno entre: APAGADO, HYPERION_UDP, STATIC_COLOR, RAINBOW, FIRE2012
   - Puede definir la configuración de Wifi pero también puede cambiarla desde la interfaz web

3. Abra el `HyperionRGB.ino`IDE de Arduino

4. Compile y suba a su placa

Fuente: https://github.com/SciLor/Hyperion_LED-Controller, https://hyperion-project.org/threads/tutorial-wireless-led-extension-with-esp8266-esp32-for-hyperion.3004/

## Fase 2. Instalación en raspberry pi con libreelec

Entrar en LibreElec por ssh y ejecutar el comando:

```bash
wget -qO- https://git.io/JU4Zx | bash
```

Si queremos eliminar Hyperion de  LibreElec, ejecutar los siguientes comandos:

```bash
systemctl disable hyperion.service --now
rm -R /storage/hyperion
```

Fuente: https://hyperion-project.org/threads/install-hyperion-ng-on-libreelec-x86_64-rpi-inoffiziell-unofficially.10463/

