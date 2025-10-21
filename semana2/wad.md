# Projeto 2 (Cricuito RC na pratica)

Neste projeto, exploramos na prática o comportamento de circuitos RC (Resistor–Capacitor).
O objetivo foi observar e medir o processo de carga e descarga de um capacitor utilizando:

* Um interruptor para controlar a alimentação do circuito;

* Um capacitor para armazenar energia elétrica;

* Resistores para controlar a corrente e criar a constante de tempo do sistema;

* Arduino Uno para aquisição dos dados em tempo real.

# Montagem

O circuito foi montado de forma que:
* O capacitor ficasse em paralelo com o resistor,

* O interruptor controlasse o fornecimento de tensão,

* O pino A0 do Arduino realizasse a leitura da tensão no resistor.

# codigo usado:

```
int pinoNoRC=0;

int valorLido = 0;

float tensaoCapacitor = 0, tensaoResistor;

unsigned long time;

void setup(){

Serial.begin(9600);

}

void loop() {

        time=millis();

        valorLido=analogRead(pinoNoRC);

        tensaoResistor=(valorLido*5.0/1023); // 5.0V / 1023 degraus = 0.0048876

        tensaoCapacitor = abs(5.0-tensaoResistor);

         Serial.print(time); //imprime o conteúdo de time no MONITOR SERIAL

    Serial.print(" ");

          Serial.print(tensaoResistor);

          Serial.print(" ");

          Serial.println(tensaoCapacitor);

        delay(400);

}
```

# Imagem do projeto:
![image](https://res.cloudinary.com/dtxiyeitw/image/upload/v1761001515/imagem_2025-10-20_200513616_xbwtf7.png)

![image](https://res.cloudinary.com/dtxiyeitw/image/upload/v1761001610/imagem_2025-10-20_200648912_edbcp0.png)

## link do projeto para simular:


# Conclusão:
* O circuito RC demonstrou claramente o comportamento de armazenamento e liberação de energia elétrica em um capacitor.
* A análise gráfica permitiu visualizar o fenômeno de carga e descarga