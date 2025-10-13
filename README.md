# Checkpoint-5-edge




Projeto IoT – Monitoramento de Temperatura, Umidade e Luminosidade com ESP32 e MQTT
 Descrição do Projeto:

Este projeto implementa um sistema de Internet das Coisas (IoT) utilizando o ESP32, que realiza a leitura dos sensores DHT11 (temperatura e umidade) e LDR (luminosidade), enviando os dados para um broker MQTT público, permitindo a visualização e o controle remoto via o aplicativo MyMQTT.

O sistema também foi desenvolvido e testado no simulador Wokwi, garantindo reprodutibilidade e fácil implementação em ambientes físicos.

 Simulação no Wokwi:
https://wokwi.com/projects/382224488947921921
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

 
 Objetivo:

Demonstrar a integração entre sensores físicos e uma plataforma de comunicação IoT via protocolo MQTT, possibilitando:

Monitorar em tempo real temperatura, umidade e luminosidade;

Enviar e receber dados do MyMQTT;

Estabelecer a comunicação entre o ESP32, o broker MQTT e o aplicativo móvel.

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Componentes Utilizados:
| Componente          | Função                               | Pino ESP32 |
| ------------------- | ------------------------------------ | ---------- |
| DHT11               | Medir temperatura e umidade          | GPIO 15    |
| LDR + resistor 10kΩ | Medir luminosidade                   | GPIO 34    |
| ESP32 DevKit V1     | Microcontrolador com Wi-Fi integrado | —          |

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


Esquemático de Ligação:
 
 Conexões:

DHT11:

VCC → 3.3V

GND → GND

DATA → GPIO 15

LDR:

LDR + resistor de 10kΩ formam um divisor de tensão

O ponto médio → GPIO 34

Um lado → 3.3V

Outro lado → GND



//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Configuração do MyMQTT:

Baixar o aplicativo MyMQTT (Android);

Abrir o app e criar uma nova conexão:

Broker: test.mosquitto.org

Porta: 1883

Client ID: MyMQTT_Andre

QoS: 0

Após conectar, adicionar os tópicos:

andre5623/temperatura

andre5623/umidade

andre5623/luminosidade

Visualize as mensagens sendo publicadas a cada 5 segundos.


//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////



Broker MQTT Público

O projeto utiliza o broker gratuito e aberto:

Broker: test.mosquitto.org

Porta: 1883



 Este broker é ideal para testes e aprendizado, mas não deve ser usado em aplicações críticas, pois os dados são públicos.


 //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


 Conclusão

O projeto demonstra com sucesso:

A coleta de dados ambientais via sensores DHT11 e LDR;

A transmissão via protocolo MQTT;

A integração entre hardware e aplicativo móvel;

O uso de brokers públicos para aplicações educacionais de IoT.

Essa implementação reforça conceitos fundamentais de IoT, conectividade Wi-Fi, comunicação assíncrona e monitoramento remoto.
