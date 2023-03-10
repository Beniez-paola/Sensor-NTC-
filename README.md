# Analog Temperature Sensor (NTC) - Sensor de temperatura analogo 

INSTITUTO TECNOLÓGICO DE TIJUANA

DEPARTAMENTO DE SISTEMAS Y COMPUTACIÓN

Carrera: Ingenieria en sistemas computacionales

Materia: Sistemas programables

Nombre del alumno: Benitez Solorzano Paola

Maestro: Rene Solis Reyes

## Introducción
Dentro de la actualidad hemos visto que existen muchos tipos de termometros pero dentro de ellos estan los termometros digitales. Normalmente para tomar la temperatura se usa un termistor fisico para checar la temperatura. Pero se puede simular un termometro digital con un analog temperature sensor, un termometro digital puede servir  para monitorear las condiciones en un invernadero o proteger su satélite del frío helado del espacio exterior.

## Vistazo 

![image](https://user-images.githubusercontent.com/124212478/224230506-39febc8d-400f-43b1-af43-c82de6f58c80.png)

![](https://user-images.githubusercontent.com/124212478/223628114-b02ce297-baf8-4899-a711-0562a73bffdf.png)


## ¿Que es un analog temperature sensor (NTC) ?
Un sensor de temperatura analógico (o de salida de voltaje) proporciona un nivel de voltaje que es directamente proporcional a la temperatura medida. En palabras simples, estos dispositivos convierten la temperatura en voltaje.

## Beneficios de usar un analog temperature sensor
* Los sensores de temperatura de silicio son lineales en un rango de temperatura más amplio, mientras que el coeficiente de temperatura de un termistor no es lineal.
* Los sensores de temperatura de silicio no requieren una corriente de excitación, lo que reduce el consumo de energía.
* Los sensores de temperatura de silicio no requieren circuitos externos, por lo que minimizan el costo y el área de la placa.

## Nombre de los pines 

| Nombre  | Descripción                      |
|---------|----------------------------------|
| VCC     | Fuente de alimentación positiva  |
| OUT     | Señal de salida (analógica)      |
| GND     | Tierra                           |

## Ejemplos de aplicaciones que se ocupan de la temperatura incluyen:
* Apagado térmico de la fuente de alimentación
* Control de termostato
* Control del ventilador
* Acondicionador de bateria automotriz
* Climatización
* Refrigerador
* Congelador
* Ollas arroceras
* Amplificador de poder

## Esquema del modulo del sensor de temperatura

![image](https://user-images.githubusercontent.com/124212478/223629096-a56b4ef3-729a-405a-9e97-c4fe01d8b0ab.png)

Este esquema se llama divisor de voltaje , porque el voltaje VCC se divide entre la resistencia y el termistor y la fracción depende de la relación entre la resistencia del termistor y la del resistor ( 10k). Con esto indica que la resistencia del termistor en sí depende de la temperatura, y se puede calcular la temperatura midiendo el voltaje en el pin de SALIDA.

## Simulando el sensor

![](/imagenes/Diagrama.jpg)

## Codigo 

```python
# Analog temperature sensor (NTC)
#Librerias importadas para el programa
from time import sleep
from machine import ADC
from math import log

# Uso de constantes
BETA = 3950 # es el coeficiente del beta del termistor
KELVIN_CONSTANT = 273.15

#Funciones
def adc_to_celsius(x):
    return (1 / (log(1/(65535/x - 1))/BETA + 1/298.15) - KELVIN_CONSTANT)

thermistor_pin = ADC(26)

#Ciclo
while True:
    thermistor_value = thermistor_pin.read_u16()
    print("Valor(ADC)","Celsius(°C)" )
    print(thermistor_value , "      ", adc_to_celsius(thermistor_value))
    sleep(0.1)

```
**Link del programa :** https://wokwi.com/projects/358690984043860993

## Resultados

> Cuando le damos clic en el boton de "iniciar simulación" estos son los resultados que aparecen.

![](/imagenes/Resultado1.jpg)

> Si queremos cambiar la temperatura, le damos clic al sensor y nos aparece este recuadro para modifcar la temperatura.

![](/imagenes/Termometro.jpg)

> Aqui se ven los cambios reflejados al mover la temperatura

![](/imagenes/Resultado2.jpg)

## Fuentes bibliograficas
* https://microchipdeveloper.com/analog:analog-temperature-sensor
* https://bhave.sh/micropython-measure-temperature/
* https://docs.wokwi.com/parts/wokwi-ntc-temperature-sensor
