## Arquitectura IoT de las pulseras LED de Shakira
### Problema a resolver

En los conciertos se utilizan miles de pulseras LED que tienen que encenderse y cambiar de color al mismo tiempo. Por ello, el sistema necesita poder enviar las órdenes rapidamente y sin tener que comunicarse individualmente con cada pulsera. 

### Arquitectura general

El funcionamiento es:
Consola de luces -> Red de control -> Transmisores IR -> Pulseras
La consola genera las órdenes y los transmisores las envían mediante luz infrarroja.

#### Composición de una pulsera

- Receptor infrarrojo
- Microcontrolador
- LEDs RGB
- Pilas

#### Uso del infrarrojo

El infrarrojo permite enviar la misma orden a muchas pulseras a la vez. Además, funciona bien en espacios grandes y evita tener que gestionar miles de conexiones individuales.

#### Sincronización

Los transmisores IR envían continuamente las órdenes. Todas las pulseras que reciben la señal ejecutan el cambio prácticamente al mismo tiempo. No hace falta que cada pulsera confirme que ha recibido el mensaje.

#### ¿Qué pasa si una señal falla?

Las órdenes se envían repetidamente. Si una pulsera recibe una señal incorrecta, simplemente la descarta y espera a la siguiente. Así se consigue que el sistema sea más sencillo y fiable.

#### De la consola a la pulsera

La consola utiliza productos como DMX, Art-Net o sACN para controlar las luces. Los transmisores convierten estas órdenes y las envían finalmente por infrarrojos a las pulseras.

#### DMX512

DMX512 es un estándar utilizado paea controlar sistemas de iluminación y permite enviar valores para controlar diferentes luces y efectos. En este sistema, las órdenes terminan transformándose en señales que reciben las pulseras.

#### ¿Cómo hacen las ondas?

Las pulseras no saben donde están situadas, el espacio se divide en diferentes zonas y cada una recibe la señal de un transmisor IR. Activando las zonas una detrás de otra se consigue el efecto de una onda de luz.

#### Ventajas del sistema

- Permite controlar miles de pulseras
- Las órdenes se reciben rápidamente
- Las pulseras son sencillas y consumen poca energía
- No es necesario que cada pulsera tenga conexión propia

#### Conclusión

Las pulseras del concierto forman un sistema IoT distribuido. La combinación de DMX, red de control, transmisores infrarrojos y pulseras sencillas permite controlar miles de dispositivos de forma sincronizada.
