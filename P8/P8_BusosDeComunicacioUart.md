# **PRÀCTICA 8: BUSOS DE COMUNICACIÓ (UART)** 
## **8.1 Codi**
```c++
#include <Arduino.h>

        char valor;
        char valor2;

        void setup() {
            Serial.begin(115200);
            Serial2.begin(115200);
        }

        void loop() {
            if(Serial.available()){
                valor = Serial.read();
                Serial2.write(valor);

                delay(2);

                if(Serial2.available()){
                    valor2 = Serial2.read();
                    Serial.write(valor2);
                }
            }
        } 
```

### **8.2 Funcionament**
En primer lloc declarem les variables valor i valor2 de tipus char, que serà el caràcter que rebrà l'uart0 i que després transmet l'uart2 i a l'inversa.

En el setup s'inicialitzara el Serial per al uart0 i el Serial2 per l'uart2.

Per últim en el loop tenim el bucle de comunicació uart. Mitjançant un if se li diu que en el moment que l'uart0 estigui disponible llegeixi el valor i així doncs l'uart2 el transmeti i ens apareixi per pantalla. Més tard es repetira el mateix procediment pero a l'inreves.

![](Practica8Uart.jpg)

