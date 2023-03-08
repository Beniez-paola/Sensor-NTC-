# Analog Temperature Sensor (NTC) - Sensor de temperatura analogo 

## Nombre del alumno: Benitez Solorzano Paola
Materia: Sistemas programables

Maestro: Rene Solis Reyes

Carrera: Ingenieria en sistemas computacionales

## Introducción
Dentro de la actualidad hemos visto que existen muchos tipos de termometros pero dentro de ellos estan los termometros digitales. Normalmente para tomar la temperatura se usa un termistor fisico para checar la temperatura. Pero se puede simular un termometro digital con un analog temperature sensor, un termometro digital puede servir  para monitorear las condiciones en un invernadero o proteger su satélite del frío helado del espacio exterior.

## Vistazo 

![image](https://user-images.githubusercontent.com/124212478/223567943-2a83e982-304f-407a-b077-5f943c8208c4.png)

![image](https://user-images.githubusercontent.com/124212478/223628114-b02ce297-baf8-4899-a711-0562a73bffdf.png)


## ¿Que es un analog temperature sensor (NTC) ?
Un sensor de temperatura analógico (o de salida de voltaje) proporciona un nivel de voltaje que es directamente proporcional a la temperatura medida. En palabras simples, estos dispositivos convierten la temperatura en voltaje.

## Beneficios de usar un analog temperature sensor
* Los sensores de temperatura de silicio son lineales en un rango de temperatura más amplio, mientras que el coeficiente de temperatura de un termistor no es lineal.
* Los sensores de temperatura de silicio no requieren una corriente de excitación, lo que reduce el consumo de energía.
* Los sensores de temperatura de silicio no requieren circuitos externos, por lo que minimizan el costo y el área de la placa.

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

![](/img/diagrama.jpg)




