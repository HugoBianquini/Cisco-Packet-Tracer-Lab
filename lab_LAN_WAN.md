# Instruções de Execução

Mãos a obra!

## 1. Arraste os equipamentos necessários para a tela de trabalho
Traga 4 computadores, 2 switches (2960) e 2 roteadores (4321) para a tela de trabalho. <br />
Disponha-os conforme a imagem abaixo:

![setup_inicial](https://user-images.githubusercontent.com/65050552/175167542-81be4b35-e9ab-4b98-8529-577e1f583a93.png)

## 2. Inicie a interconexção da primeira LAN (Rio de Janeiro)

Nessa etapa, você deve interligar o switch0 com os PCs 0 e 1 e o Router0.
Siga a tabela de portas do switch representada abaixo:

|Porta (Switch0)| Equipamento Destino | Porta Destino |
|---------------|---------------------|---------------|
|fastEthernet 0/1 | PC 0              | fastEthernet 0|
|fastEthernet 0/2 | PC 1              | fastEthernet 0|

Replique essas conexões para a LAN de São Paulo

## 3. Setup Físico dos Roteadores

Antes de realizar conexões de longa distância, os roteadores devem ser equipados com uma placa apropriada para esse tipo de conexão.

Para isso, será necessário:
#### 1. Desligar o Roteador
#### 2. Abrir a interface do Roteador (apenas clique em cima do equipamento para abrir)
#### 3. Desligue o roteador (garanta que esteja na aba `physical`
#### 4. Clique na placa no canto direito inferior na interface do roteador e arraste até um dos compartimentos disponíveis no roteador, conforme a imagem abaixo:
<br />

![placa_roteador](https://user-images.githubusercontent.com/65050552/175170281-98270db8-84f2-476c-804d-c21858e183e5.png)

#### 5. Replique esses passos para o outro roteador.


## 4. Configuração dos roteadores
Nessa etapa nós definiremos os IPs das portas do roteador e os conectaremos com os Switches

Primeiro, conecte o Roteador ao Switch seguindo a seguinte tabela de portas inicial do roteador

|Porta (Router0)| Equipamento Destino | Porta Destino |
|---------------|---------------------|---------------|
|GigabitEthernet 0/0/0 | Switch0              | GigabitEthernet 0/1|

Feita a conexão, abra a interface do roteador, vá até a aba `config` e selecione a porta GigabitEthernet0/0/0. Preencha a configuração IP da seguinte forma:

|IPv4 Address| Subnet Mask |
|------------|-------------|
|192.168.20.1| 255.255.255.0|

Após isso, preecha a caixa de seleção `on` para ativar a porta do roteador.
<br />
Replique esses passos para o Router1
