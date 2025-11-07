# ActividadArquitectura-5-11-25
Varela Alan Christian Emmanuel

#Consignas
Implementar la aplicaciòn en Arduino Uno en Wokwi del proyecto:
https://www.aprendemachinelearning.com/programa-un-coche-arduino-con-inteligencia-artificial/

1- Hacer un resumen de las arquitecturas observadas en el proyecto

2- Mencionar los enfoques de resolución de problemas aplicados

3- Ejecutar el colab para entrenar la red neuronal

4- Simular 2 entradas nuevas y 1 salida más. Modificar y ajustar nuevamente la red neuronal.
Por cada miembro del equipo generar una nueva tabla de verdad y desplegarla nuevamente.

5- Confeccionar github con el código y en el Readme resumir todo lo solicitado.


#Desarrollo

Implementación en Wokwi
https://wokwi.com/projects/446824758623098881


1-	Arquitecturas.
Se usan 2 arquitecturas: una en Python y otra en Arduino.
La primera entrena la red neuronal en entorno de Python antes de implementar en Arduino. La red utiliza un patrón multicapa con 2 neuronas de entrada, 3 neuronas en la capa oculta y 4 neuronas de salida, una por cada motor. El entrenamiento usa un algoritmo de backpropagation y combina detecciones de obstáculos en la entrada y encendido y apagado de motores en la salida. Esto genera las matrices de pesos HiddenWeights y OutputWeights con el conocimiento aprendido, que se exportan en formato C para ser usadas con el código Arduino.
La segunda implica un sistema embebido de hardware/software. Se ejecuta una versión del modelo neuronal simplificada para trabajar en tiempo real con los sensores. Se utiliza un microcontrolador ATmega328P con arquitectura de hardvard, sensores ultrasónicos para detectar obstáculos y salidas que activan los motores. Por otra parte se implementa el código en C usando los pesos entrenados.

2-	Enfoques de resolución de problemas
En el proyecto se aplicaron diferentes metodologías para solucionar problemas.
Enfoque algorítmico: Primero, se podría haber resuelto el problema de sortear los obstáculos con un algoritmo fijo, pero no contemplaría todas las combinaciones posibles, por eso se decidió usar una red neuronal que aprenda por si sola los patrones de comportamiento.
Enfoque de inteligencia artificial: El principal problema del proyecto era que el coche detectara los obstáculos y decidiera cómo moverse, por lo que se aplicó un enfoque de aprendizaje supervisado en el que se recolectan ejemplos de comportamientos, se entrena una red neuronal para que aprenda esas relaciones con ajuste de pesos y los implemente en Arduino, sin que el coche tenga que usar reglas fijas. El Arduino entonces no tiene que pensar, sino que aplica el conocimiento aprendido por la red neuronal.
Enfoque de descomposición modular: EL proyecto se resolvió dividiendo el problema en módulos más simples: módulos que detectan los obstáculos (sensor ultrasónico), procesan y deciden la acción (red neuronal) y ejecutan la acción elegida (control de motores).

3 y 4- https://colab.research.google.com/drive/1QzbxvDw2fnq92BE8dPBoWUiXU1XiMZZo?usp=sharing


