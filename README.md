# Controle de LED via MQTT com ESP32 e Atom Dashboard

Este projeto permite controlar um LED conectado ao ESP32 utilizando o protocolo MQTT. O ESP32 se conecta a um broker MQTT e recebe comandos para ligar e desligar o LED. O controle pode ser feito utilizando o aplicativo **Atom Dashboard** para Android.

## 📌 Funcionalidades
- Conexão do ESP32 a uma rede Wi-Fi
- Comunicação com o broker MQTT **HiveMQ**
- Controle remoto do LED via mensagens MQTT
- Compatível com o aplicativo **Atom Dashboard**

## 🔧 Hardware Necessário
- ESP32
- LED
- Resistor (220Ω recomendado)
- Protoboard e jumpers

## 📲 Aplicativo Atom Dashboard
O **Atom Dashboard** é utilizado para enviar comandos MQTT ao ESP32. Para configurá-lo:
1. Baixe o **Atom Dashboard** na Play Store.
2. Adicione um novo widget do tipo "Switch".
3. Configure o widget com os seguintes parâmetros:
   - **Broker:** `broker.hivemq.com`
   - **Porta:** `1883`
   - **Tópico:** `seu_usuario/esp32/led`
   - **Mensagem ON:** `ON`
   - **Mensagem OFF:** `OFF`
4. Salve e utilize o switch para ligar/desligar o LED.

## 🔌 Instalação e Configuração
### 1️⃣ Instale as bibliotecas necessárias na IDE Arduino
Certifique-se de ter as seguintes bibliotecas instaladas:
- **WiFi** (inclusa no Arduino IDE para ESP32)
- **PubSubClient** (para comunicação MQTT)

Para instalar a **PubSubClient**:
1. Abra a IDE Arduino
2. Vá para **Sketch** > **Incluir Biblioteca** > **Gerenciar Bibliotecas**
3. Pesquise por **PubSubClient** e instale

### 2️⃣ Faça o upload do código para o ESP32
- Conecte o ESP32 ao seu computador via USB
- Copie e cole o código no Arduino IDE
- Substitua `ssid` e `password` pelas credenciais da sua rede Wi-Fi
- Faça o upload do código para o ESP32

### 3️⃣ Verifique a Conexão
- Abra o **Monitor Serial** na IDE Arduino (115200 baud)
- O ESP32 tentará se conectar ao Wi-Fi e ao broker MQTT
- Se a conexão for bem-sucedida, você verá mensagens indicando a assinatura do tópico

## 📝 Código-fonte
O código-fonte do projeto está disponível no arquivo `main.ino` e implementa:
- Conexão Wi-Fi
- Conexão ao broker MQTT
- Callback para interpretar mensagens recebidas
- Controle do LED com os comandos `ON` e `OFF`

## 📡 Broker MQTT
O broker utilizado neste projeto é o **HiveMQ** (`broker.hivemq.com`), que é um serviço gratuito e público de MQTT. Caso precise de mais segurança e estabilidade, considere hospedar seu próprio broker.

## 🚀 Melhorias Futuras
- Adicionar autenticação no MQTT para maior segurança
- Expandir o projeto para controlar múltiplos dispositivos
- Criar uma interface web para controle adicional

## 📜 Licença
Este projeto é de código aberto e está licenciado sob a **MIT License**.

