# CAJERO-AUTOMATICO-CON-USART
codigo de cajero en stm32 usando Usart

Este código es un ejemplo de un programa para un microcontrolador STM32L053R8 que implementa un sistema de manejo de saldo simple mediante comunicación serial. les dejamos una  explicación detallada de cada parte del código:

primero muestra un mensaje en la consola de las opciones disponibles
![image](https://github.com/ByronRC89/CAJERO-AUTOMATICO-CON-USART/assets/159856194/2e670f45-fdd8-480f-9bb7-9db6e112b4ad)

Inclusión de bibliotecas
```#include <stdint.h>:``` Incluye la biblioteca estándar de tipos de datos enteros definidos (stdint.h).
Inclusiones de bibliotecas específicas del microcontrolador STM32L053xx.
Variables globales
**saldo:** Variable global que almacena el saldo actual.
![image](https://github.com/ByronRC89/CAJERO-AUTOMATICO-CON-USART/assets/159856194/d63748f3-ef52-4b10-91fb-489933be1030)

Declaraciones de funciones
```void delay_ms(uint16_t n):``` Prototipo de función para una función que genera un retardo en milisegundos.
```void USART2_write(uint8_t ch):``` ejemplo de función para enviar un byte a través del módulo USART2.
```void USART2_putstring(uint8_t* StringPtr):``` ejemplo de función para enviar una cadena de caracteres a través del módulo USART2.
```void USART2_putstring_E(uint8_t* StringPtr):``` ejemplo de función para enviar una cadena de caracteres seguida de un retorno de carro (CR) y un salto de línea (NL) a través del módulo USART2.
```uint8_t USART2_read(void):```  función para leer un byte recibido a través del módulo USART2.
```void consultar_saldo(void):```  función para consultar y enviar el saldo actual a través del módulo USART2.
```void realizar_deposito(uint32_t monto):``` función para realizar un depósito en la cuenta y enviar un mensaje de confirmación a través del módulo USART2.
```void realizar_retiro(uint32_t monto):```  función para realizar un retiro de la cuenta y enviar un mensaje de confirmación o de saldo insuficiente a través del módulo USART2.

**Función main()**
Configura los pines del microcontrolador para la comunicación USART2 y la salida de un mensaje en el pin PA5.
Inicia la comunicación USART2 con una velocidad de baudios de 9600.
Entra en un bucle infinito donde espera a que el usuario escriba los caracteres mmostrados en la pantalla de la consola y realizar acciones como consultar saldo, depositar o retirar dinero.

**Funciones de saldo y comunicación USART2**

```consultar_saldo():``` Imprime el saldo actual a través de la comunicación USART2.
```realizar_deposito(uint32_t monto):``` Realiza un depósito en la cuenta y actualiza el saldo, luego envía un mensaje de depósito exitoso a través de la comunicación USART2.
```realizar_retiro(uint32_t monto):``` Verifica si hay suficiente saldo para realizar un retiro, si es así, se realiza el retiro y se actualiza el saldo, de lo contrario, envía un mensaje de saldo insuficiente a través de la comunicación USART2.
```USART2_read(): ```Lee un byte recibido a través del módulo USART2.
```USART2_write(uint8_t ch):``` Envía un byte a través del módulo USART2.
```USART2_putstring(uint8_t* StringPtr):``` Envía una cadena de caracteres a través del módulo USART2.
```USART2_putstring_E(uint8_t* StringPtr):``` Envía una cadena de caracteres seguida de un retorno de carro y un salto de línea a través del módulo USART2.
```void delay_ms(uint16_t n)``` Genera un retardo en milisegundos.

**imagenes de funcionamiento y operacion en consola.**
![image](https://github.com/ByronRC89/CAJERO-AUTOMATICO-CON-USART/assets/159856194/f42a2427-9ab4-4274-b3d1-6022771d4fd3)
en esta igamen mostramos en codigo como se estara enviando a la consla como menu principal.

con la letra S consultamos saldo y nos mostrara el saldo definido en programa,
![image](https://github.com/ByronRC89/CAJERO-AUTOMATICO-CON-USART/assets/159856194/97d3e7a2-987f-4c65-aa1b-0885cc6f7ad9)

S presionamos cualquier opcion ya sea retiro o deposito, el monto elegido sera mostrado en la diferencia del valor mostrado
mostremos el deposito de 10 dolares
![image](https://github.com/ByronRC89/CAJERO-AUTOMATICO-CON-USART/assets/159856194/b7947ab6-94ac-44ef-bbf1-4463d5ad04d6)

mostremos un retiro de 50 dolares.
![image](https://github.com/ByronRC89/CAJERO-AUTOMATICO-CON-USART/assets/159856194/3ab7264c-aead-4967-9ea7-e545e71146af)

mostremos un retino no exitoso y por que. al retirar 500 dolares el sistema me reconoce que el saldo son 460
por lo que en mi 5to retiro me muestra que el saldo es insuficiente y al consultar efectivamente solo tengo 60.
![image](https://github.com/ByronRC89/CAJERO-AUTOMATICO-CON-USART/assets/159856194/903b5fa2-5bdb-443e-a576-114af38be00c)


adjunto video de una explicacion breve https://www.youtube.com/watch?v=CB4owvAr_TA ![image](https://github.com/ByronRC89/CAJERO-AUTOMATICO-CON-USART/assets/159856194/d7321c08-1f15-453d-bb35-429bc9980edf)


gracias.
