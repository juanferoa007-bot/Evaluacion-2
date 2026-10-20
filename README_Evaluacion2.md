# Evaluación 2 --- Introducción a Tecnologías de Información

**Estudiante:** \[Escribe tu nombre completo\]\
**Asignatura:** Introducción a Tecnologías de Información\
**Actividad:** Cuestionario Segundo Momento

------------------------------------------------------------------------

## Pregunta 1. Duración del ciclo del semáforo

**Respuesta correcta: D. 11000 milisegundos.**

**Justificación:** El ciclo completo suma los tiempos de las tres luces:
verde durante 5000 ms, amarillo durante 2000 ms y rojo durante 4000 ms.
Por tanto, (5000 + 2000 + 4000 = 11000) milisegundos, equivalentes a 11
segundos.

## Pregunta 2. Detección de errores de sintaxis

**Respuesta correcta: C. Ejecutar el subcomando `compile` e indicar el
identificador de la placa.**

**Justificación:** El subcomando `compile` de Arduino CLI compila el
sketch y permite detectar errores de sintaxis antes de conectar o cargar
el programa en la placa. Para Arduino UNO R3 se puede usar el
identificador `arduino:avr:uno`, siempre que el núcleo correspondiente
esté instalado.

## Pregunta 3. Contador binario de cuatro bits

**Respuesta correcta: D. Los LEDs de los bits 0, 2 y 3.**

**Justificación:** El número decimal 13 se representa en binario de
cuatro bits como `1101`. Los bits 0, 2 y 3 tienen valor 1, mientras que
el bit 1 tiene valor 0. Por eso permanecen encendidos los LEDs
correspondientes a los bits 0, 2 y 3.

## Pregunta 4. Varias lecturas por una pulsación

**Respuesta correcta: C. Ignorar nuevas lecturas durante un breve
intervalo tras detectar el primer cambio.**

**Justificación:** El rebote mecánico del pulsador genera varias
transiciones eléctricas en pocos milisegundos. La técnica de antirrebote
(*debounce*) filtra esas transiciones, por ejemplo, ignorando nuevas
lecturas durante un intervalo breve después de detectar la primera
pulsación válida.

## Pregunta 5. Patrones seleccionables con un DIP switch

**Respuesta correcta: A. 4 patrones.**

**Justificación:** Los canales 1 y 2 seleccionan el patrón de los LEDs.
Dos interruptores binarios tienen (2\^2 = 4) combinaciones posibles. Los
canales 3 y 4 seleccionan la velocidad del efecto, no el patrón de
encendido.

## Pregunta 6. Lectura con `INPUT_PULLUP`

**Respuesta correcta: D. Nivel LOW porque el contacto cerrado impone una
tensión de cero voltios.**

**Justificación:** Con `INPUT_PULLUP`, la resistencia interna mantiene
normalmente el pin en HIGH. Cuando el interruptor se coloca en ON y
conecta el pin a tierra, la tensión cae aproximadamente a 0 V y
`digitalRead()` devuelve LOW.

## Pregunta 7. Duración de un efecto de persecución

**Respuesta correcta: B. 800 milisegundos.**

**Justificación:** En una ida y vuelta de seis LEDs, con cada extremo
encendido una sola vez, se recorren diez posiciones: seis en la ida y
cuatro en el regreso, sin repetir los extremos. Cada paso dura 80 ms,
así que (10 `\times 80`{=tex} = 800) milisegundos.

## Pregunta 8. Permiso denegado en el puerto serie

**Respuesta correcta: A. Agregar el usuario al grupo `dialout` y
reiniciar su sesión en Debian 13.**

**Justificación:** En Debian, el acceso a puertos serie como
`/dev/ttyACM0` suele controlarse mediante permisos de grupo. Agregar el
usuario al grupo `dialout` y volver a iniciar sesión permite que los
nuevos permisos se apliquen. Se debe usar una cuenta autorizada y seguir
las normas del sistema.

## Pregunta 9. Conversión de una lectura ADC a PWM

**Respuesta correcta: D. 204.**

**Justificación:** La función `map()` convierte la lectura de 0--1023 al
rango 0--255. El cálculo aproximado es (819 `\times 255`{=tex} / 1023
`\approx 204.2`{=tex}). Como `map()` devuelve un valor entero en este
caso, el resultado es 204.

## Pregunta 10. Velocidad del monitor serial

**Respuesta correcta: C. El monitor muestrea los bits con una tasa
distinta a la configurada en el sketch.**

**Justificación:** El sketch inicia la comunicación a 9600 baudios, pero
el monitor serial está configurado a 115200. Al no coincidir las
velocidades, los datos se interpretan incorrectamente y aparecen
caracteres ilegibles. Ambas configuraciones deben usar la misma
velocidad.

## Pregunta 11. Constante de tiempo de un circuito RC

**Respuesta correcta: C. 4,7 segundos.**

**Justificación:** La constante de tiempo se calcula con (`\tau `{=tex}=
R `\times `{=tex}C). Con (R = 10,000 `\Omega`{=tex}) y (C =
470 `\mu `{=tex}F = 0.00047 F), se obtiene (`\tau `{=tex}= 10,000
`\times 0.00047`{=tex} = 4.7) segundos.

## Pregunta 12. Carga y descarga del capacitor

**Respuesta correcta: A. Solo la declaración 1 es verdadera.**

**Justificación:** Durante la descarga, la tensión del capacitor
disminuye exponencialmente hacia cero, por lo que la primera declaración
es verdadera. Después de una constante de tiempo de carga, el capacitor
alcanza aproximadamente el 63,2 % de la tensión de la fuente, no el 100
%, así que la segunda declaración es falsa.

## Pregunta 13. Corriente de base del transistor 2N2222

**Respuesta correcta: B. 4,3 miliamperios.**

**Justificación:** La tensión sobre la resistencia de base es
aproximadamente (5 - 0.7 = 4.3) V. Aplicando la ley de Ohm, (I = V/R =
4.3 V / 1000 `\Omega `{=tex}= 0.0043 A), es decir, 4,3 mA.

## Pregunta 14. Diodo de protección de un motor

**Respuesta correcta: B. Ambas proposiciones son verdaderas y la razón
sustenta directamente la afirmación.**

**Justificación:** La bobina del motor puede generar una tensión
inducida de polaridad inversa cuando se interrumpe la corriente. El
diodo en paralelo proporciona un camino para esa corriente y limita el
pico de tensión, ayudando a proteger el transistor.

## Pregunta 15. Pin PWM del Arduino UNO R3

**Respuesta correcta: C. Pin digital 9.**

**Justificación:** En Arduino UNO R3, los pines compatibles con PWM son
3, 5, 6, 9, 10 y 11. De las opciones dadas, el pin 9 es el único que
dispone de esa capacidad.

## Pregunta 16. Control de un relé mediante transistor

**Respuesta correcta: D. Porque la demanda de la bobina excede la
capacidad de corriente que soporta el pin.**

**Justificación:** La bobina requiere 72 mA, mientras que el enunciado
indica un máximo de 40 mA por pin digital. Conectar la bobina
directamente podría sobrecargar y dañar el pin. Un transistor permite
controlar esa carga con una señal de menor corriente.

## Pregunta 17. Circuito de la bobina y contactos del relé

**Respuesta correcta: B. Solo la declaración 2 es verdadera.**

**Justificación:** La bobina del relé y los contactos que controlan el
motor son circuitos eléctricamente separados; por eso la declaración 1
es falsa. El diodo en paralelo con la bobina limita el pico de tensión
al interrumpirse la corriente, por lo que la declaración 2 es verdadera.

## Pregunta 18. Diferencia entre umbrales de activación y desactivación

**Respuesta correcta: A. Los cierres y aperturas repetidos del relé
cuando la señal fluctúa alrededor de un único valor.**

**Justificación:** Usar dos umbrales distintos ---activar por encima de
700 y desactivar por debajo de 600--- crea histéresis. Esta evita que
pequeñas fluctuaciones cerca de un solo umbral hagan que el relé se
active y desactive repetidamente.

## Pregunta 19. Microinterruptor y buzzer al abrir una puerta

**Respuesta correcta: D. El pin 2 lee nivel LOW y el sketch activa el
buzzer con la función `tone()`.**

**Justificación:** Al abrirse la puerta, el contacto que conectaba el
pin a 5 V se abre. La resistencia pull-down mantiene el pin a nivel LOW.
Según el enunciado, esa detección de apertura activa el buzzer mediante
`tone()`.

## Pregunta 20. Función `tone()` en un buzzer pasivo

**Respuesta correcta: B. La afirmación es verdadera, mientras que la
razón es falsa.**

**Justificación:** `tone()` genera una señal periódica en el pin con una
frecuencia determinada, lo que permite producir un tono en un buzzer
pasivo. No mantiene simplemente un nivel HIGH constante; por eso la
razón es falsa.

## Pregunta 21. Fotorresistencia en un divisor de voltaje

**Respuesta correcta: A. Disminuye porque la LDR aumenta su resistencia
y la resistencia fija recibe menos tensión.**

**Justificación:** Cuando disminuye la luz, la resistencia de la LDR
aumenta. Como la LDR está entre 5 V y A0, y la resistencia fija está
entre A0 y tierra, el aumento de la resistencia superior reduce la
tensión medida en A0; por tanto, la lectura analógica disminuye.

## Pregunta 22. Indicador VU-meter de cinco LEDs

**Respuesta correcta: A. 2 LEDs.**

**Justificación:** La conversión entera de 0--1023 a 0--5 mediante
`map()` da aproximadamente (450 `\times 5`{=tex} / 1023
`\approx 2.19`{=tex}). Al descartar la parte decimal, el resultado es 2,
por lo que quedan encendidos dos LEDs.

## Pregunta 23. Secuencia del cruce peatonal

**Respuesta correcta: C. II, I, III, IV.**

**Justificación:** La secuencia segura es que el semáforo vehicular pase
primero a amarillo (II), luego a rojo (I), después el semáforo peatonal
pase a verde (III) y, al terminar, el peatonal vuelva a rojo y el
vehicular a verde (IV).

## Pregunta 24. Primer comando serial no recibido

**Respuesta correcta: B. La placa se reinicia al abrirse el puerto serie
y tarda unos segundos en iniciar el sketch.**

**Justificación:** Al abrir el puerto serie, el Arduino UNO R3 puede
reiniciarse automáticamente. Si Python envía el comando inmediatamente,
el sketch quizá todavía no esté listo para recibirlo. Esperar brevemente
a que termine el reinicio antes de enviar el comando ayuda a evitar el
problema.

## Pregunta 25. Soporte de placa ausente en Arduino CLI

**Respuesta correcta: D. Ejecutar `core update-index` y `core install`
con el paquete `arduino:avr`.**

**Justificación:** El identificador `arduino:avr:uno` pertenece al
núcleo Arduino AVR. Si el soporte de la placa no está instalado, primero
se actualiza el índice de paquetes y después se instala el núcleo
`arduino:avr`. Tras instalarlo, se puede volver a compilar el sketch.

------------------------------------------------------------------------

## Conclusión

El cuestionario aborda el uso de Arduino CLI, la programación de Arduino
UNO R3, las entradas y salidas digitales y analógicas, la comunicación
serial, los circuitos RC, los transistores, los relés y sensores. Las
justificaciones muestran el razonamiento o cálculo utilizado para
seleccionar cada respuesta.

**Antes de entregar:** reemplaza `[Escribe tu nombre completo]` por tu
nombre y revisa que el formato coincida con las instrucciones de tu
docente.
