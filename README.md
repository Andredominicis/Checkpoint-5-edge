# Checkpoint-5-edge



Projeto IoT – Monitoramento de Temperatura, Umidade e Luminosidade via ESP32 e MQTT
 
 
 Descrição Geral

Este projeto tem como objetivo monitorar a temperatura, umidade e luminosidade ambiente utilizando um ESP32, com sensores DHT22 e LDR, e enviar os dados para um servidor MQTT público (broker.hivemq.com).
As informações podem ser visualizadas e controladas em tempo real através do aplicativo MyMQTT, que atua como cliente MQTT.



//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

 
Objetivos:

Realizar leitura contínua de temperatura, umidade e luminosidade.

Publicar os dados em um broker MQTT público.

Visualizar e interagir com os dados via aplicativo MyMQTT.

Permitir a replicação do projeto em qualquer ambiente com ESP32.

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

| Componente             | Função                          | Pino ESP32              |
| ---------------------- | ------------------------------- | ----------------------- |
| ESP32 DevKit V1        | Microcontrolador principal      | -                       |
| DHT22                  | Sensor de temperatura e umidade | D15                     |
| LDR + resistor de 10kΩ | Sensor de luminosidade          | D34 (entrada analógica) |
| LED                    | Indicador de atividade          | D2 (onboard)            |


//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


Esquemático de Ligação:
 
 Conexões:

DHT22:

VCC → 3.3V

GND → GND

DATA → GPIO 15

LDR:

Um lado → 3.3V

Outro lado → D34 + resistor 10kΩ para o GND

LED: (onboard)

D2 → LED integrado do ESP32



//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Configuração do Aplicativo MyMQTT:

Host: broker.hivemq.com

Port: 1883

SSL: Desativado

Protocol: MQTT v3

Username e Password: (deixe em branco)

Client ID: Celular_Andre (ou qualquer outro nome)

Assinatura (subscribe):

/andre5623/esp32/attrs


Publicação (publish):

/andre5623/esp32/cmd


Comandos aceitos:

LED_ON → liga o LED

LED_OFF → desliga o LED

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////



Broker MQTT Público

O projeto utiliza o broker gratuito e aberto:

Broker: broker.hivemq.com

Porta: 1883



 Este broker é ideal para testes e aprendizado, mas não deve ser usado em aplicações críticas, pois os dados são públicos.


 //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


Funcionamento Geral:

O ESP32 lê temperatura, umidade e luminosidade a cada 5 segundos.

Envia os dados em formato JSON para o tópico MQTT.

O aplicativo MyMQTT recebe os dados em tempo real.

O usuário pode enviar comandos para ligar/desligar o LED remotamente.





//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////



Como Replicar o Projeto:

Crie uma conta no Wokwi

Monte o circuito conforme o esquema.

Copie o código disponibilizado neste repositorio e rode a simulação.

No celular, configure o MyMQTT com os parâmetros indicados.

Observe os dados sendo recebidos em tempo real e envie comandos.
