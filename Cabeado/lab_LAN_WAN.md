# Instruções de Execução

Mãos a obra!

## 1. Arraste os equipamentos necessários para a tela de trabalho
Traga 4 computadores, 2 switches (2960) e 2 roteadores (4321) para a tela de trabalho. <br />

|PC |  Switch | Roteadores |
|---------------|---------------------|---------------|
|![PC](https://user-images.githubusercontent.com/65050552/175389679-7b356c2a-c42a-4a79-9977-38b967857a54.png) | ![switch](https://user-images.githubusercontent.com/65050552/175389748-3caba68a-32cd-461c-9f81-36cf9f065f19.png) | ![router](https://user-images.githubusercontent.com/65050552/175389860-c458a6e8-0e7d-436d-9eb2-6575b353232e.png) |


Disponha-os conforme a imagem abaixo:!


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
#### 1. Abrir a interface do Roteador (apenas clique em cima do equipamento para abrir)
#### 2. Desligue o roteador (garanta que esteja na aba `physical`
#### 3. Clique na placa no canto direito inferior na interface do roteador e arraste até um dos compartimentos disponíveis no roteador, conforme a imagem abaixo:
<br />

![placa_roteador](https://user-images.githubusercontent.com/65050552/175170281-98270db8-84f2-476c-804d-c21858e183e5.png)

#### 5. Replique esses passos para o outro roteador.


## 4. Configuração dos roteadores
### 4.1 Conexão com Switches
Nessa etapa nós definiremos os IPs das portas do roteador e os conectaremos com os Switches

Primeiro, conecte o Roteador ao Switch seguindo a seguinte tabela de portas do roteador

Equipamento Origem |Porta Origem    | Equipamento Destino | Porta Destino |
-------------------|----------------|---------------------|---------------|
Router 0           |GigabitEthernet 0/0/0 | Switch0              | GigabitEthernet 0/1|
Router 1           |GigabitEthernet 0/0/0 | Switch1              | GigabitEthernet 0/1|

### 4.2 Configuração IP
Feita a conexão, abra a interface do roteador, vá até a aba `config` e selecione a porta GigabitEthernet0/0/0. Preencha a configuração IP da seguinte forma:

Router |IPv4 Address| Subnet Mask |
-------|------------|-------------|
Router 0|192.168.20.1| 255.255.255.0|
Router 1|168.227.20.1| 255.255.0.0|

Após isso, preecha a caixa de seleção `on` para ativar a porta do roteador.
<br />

## 5. Configuração dos PCs

### 5.1. Default Gateway

Abra a interface do PC, vá para a aba `config` e preencha o Default Gateway.
Siga a tabela abaixo:

|PC          | DEFAULT GATEWAY |
|------------|-------------|
|PC0 | 192.168.20.1|
|PC1 | 192.168.20.1|
|PC2 | 168.227.20.1|
|PC3 | 168.227.20.1|

### 5.1. Endereços IP

Uma vez preenchido os DEFAULT GATEWAYS, agora é necessário configurar o IP dos PCs.<br >
Para isso, enquanto está na aba `config`, seleciona a opção `FastEthernet0`

Ao entrar na interface da porta `FastEthernet0`, você conseguirá inserir o IP e a SubnetMask dos PCs.<br />
Siga a tabela abaixo:

PC |IPv4 Address| Subnet Mask |
---|------------|-------------|
PC0|192.168.20.2| 255.255.255.0|
PC1|192.168.20.3| 255.255.255.0|
PC2|168.227.20.2| 255.255.0.0|
PC3|168.227.20.3| 255.255.0.0|

## 6. Finalização da LAN

Com todos os passos anteriores seguidos, você já deve ter 2 LANs (RJ e SP) operacionais.<br />
Seu projeto deve estar parecido com esse:

![setup_lan](https://user-images.githubusercontent.com/65050552/175181996-0f26ab1b-5714-4417-b86e-f0d1ece34f94.png)

## 7. Configuração da WAN

Como as LANs RJ e SP estão separadas por uma grande distância, precisaremos configurar uma WAN para interconectar essas 2 redes locais.

Isso será feito conectando nossos 2 roteadores, `Router0` e `Router1`.

Será necessário que você os conecte utilizando o cabo Serial DCE, já que será uma conexão de longa distância.

Conecte a porta `Serial 0/1/0` do `Router0` na porta `Serial 0/1/0` do `Router1`

## 8. Configurar portas serial dos roteadores

Abra a interface do roteador e vá para a aba `config`. <br/ >
Selecione a porta `Serial 0/1/0` e preencha a configuração de IP conforme a tabela abaixo:


Router |IPv4 Address| Subnet Mask |
-------|------------|-------------|
Router0|200.10.0.1  | 255.255.255.0|
Router1|200.10.0.2  | 255.255.255.0|

Após a conexão, seus roteadores devem estar parecidos com essa imagem:

![roteadores](https://user-images.githubusercontent.com/65050552/175185706-2d3e9d23-8051-4d77-9075-3278c17b7c5d.png)

## 9. Configurar protocolo RIP

Para que os roteadores consigar "escutar" as redes, precisamos configurar o protocolo RIP e indicar quais redes devem ser "escutadas"

Para isso, ainda na aba `config` na interface do roteador, selecione a opção `RIP`.

Insira as redes no campo `Network` e precione o botão `Add`.<br />
Insire uma rede de cada vez: <br />

|Rede         |
|-------------|
|192.168.20.0 |
|200.10.0.0   |
|168.227.20.0 |


Ao final, sua interface deve estar dessa forma:
<br />

![RIP](https://user-images.githubusercontent.com/65050552/175185412-9974634b-29a4-498a-b80a-dcb1f88f413f.png)


## 10. Finalização

Pronto! Você conseguiu configurar 2 redes locais e uma rede WAN para conectá-las.<br />
Agora você pode testar enviando pacotes de uma rede para outra, como no vídeo abaixo:



![Cisco Packet Tracer 2022-06-22 22-11-59 (1)](https://user-images.githubusercontent.com/65050552/175187117-291371f0-1989-4971-88bf-9b71bf6fb51c.gif)



