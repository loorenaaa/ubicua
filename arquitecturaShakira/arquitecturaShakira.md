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

#### 
