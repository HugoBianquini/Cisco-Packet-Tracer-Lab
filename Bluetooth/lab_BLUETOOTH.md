# Criando Rede Bluetooth

Vamos lá!

## 1. Começando pelo início

### 1.1. O que é uma Rede Bluetooth?

A Rede Bluetooth é uma tecnologia de comunicação sem fio desenvolvida em 1994. Essa rede permite que seja realizado a troca de dados e arquivos entre celulares, computadores, scanners, fones de ouvido e demais dispositivos, que estejam relativimente perto fisicamente, de forma rápida e segura. Dessa forma, nesse laboratório iremos simular uma conecção Bluetooth entre uma caixa de som e um celular.

### 1.2. Aparelhos Utilizados

Vamos primeiramente escolher nossos aparelhos. Para este exemplo iremos usar um Bluetooth Speaker (som) e um Portable Music Player (celular). <br/>
![dsBuffer bmp](https://user-images.githubusercontent.com/106887744/175208991-e5a4a602-db40-4f89-af51-59e9adef9f0e.png)
<br/>
![celular bmp](https://user-images.githubusercontent.com/106887744/175209509-82a9ec2f-91d8-4f70-8142-9fc460486dc0.png)
<br/>

### 1.2.1 Vídeos Aparelhos Utilizados

https://user-images.githubusercontent.com/106887744/175618729-4500cd74-1af5-44af-b880-a09468ea2aba.mp4


## 2. Configurando a Rede
Primeiramente é importante alanalisarmos as informações dos aparelhos.

####2.1. Informações do Bluetooth Speaker (som)

![info_som](https://user-images.githubusercontent.com/106887744/175612894-825d28d3-eb52-4211-91ce-ac79084861a8.png)<br/>

Nessa imagem é possível observa dados interessantes de serem destacados: o "Device Name : IoT0" identifica que é um aparelho de internet das coisas, o "IP Address" do aparelho que é 169.254.158.206/16 para o Wireless, o "MAC Address" no qual tem o de origem que é 0001.6310.9ECE  e o de destino que é 00E0.F7EA.42C7.

### 2.2. Informações do Portable Music Player (celular)

![info_celular](https://user-images.githubusercontent.com/106887744/175614450-611d29c5-bd17-4e34-949c-92a3f5980c40.png)

Nessa imagem é possível observa dados interessantes de serem destacados: o "Device Name : IoT1" identifica que é um aparelho de internet das coisas, o "IP Address" do aparelho que é 169.254.162.102/16 para o Wireless, o "MAC Address" no qual tem o de origem que é 0002.1715.A266  e o de destino que é 0060.5CCD.EDB6.

### 2.3. Configurando os aparelhos

Nessa parte iremos ativar o Bluetooth de ambos aparelhos, para isso é necessário desativar o Wireless de ambos os aparelhos, visto que o Bluetooth 5.0 (que normalmente é utilizado nos fones) utiliza a frequência 2.4Ghz a mesma dos roteadores padrão e devido a isso pode haver uma interferência entre os sinais. Para realizar essa configuração é preciso clicar em cima do aparelho, com isso irá abrir uma página sobre o aparelho. Nessa página, selecione "config" localizado no menu superior, primeiro selecione no menu lateral a opção "Wireless" e desative a opção "on". Após isso, selecione no menu lateral a opção "Bluetooth" e ative a opção "on". Esse processo deve ser realizado em ambos aparelhos.

#### 2.3.1 Vídeo de Configuração do Bluetooth Speaker
https://user-images.githubusercontent.com/106887744/175616524-f90d7598-2bef-4c4b-a4ab-476481e7e182.mp4

#### 2.3.2 Vídeo de Configuração do Portable Music Player
https://user-images.githubusercontent.com/106887744/175616983-e078a7da-ba7a-40da-8a0a-479785804314.mp4


### 2.2. Conectando os aparelhos

Nessa parte, iremos realizar a conecção de Bluetooth entre os aparelhos. Primeiramente na mesma aba de "config" do aparelho e apertamos em "Discover" no qual ele irá procurar por aparelhos para parear. Após realizar essa etapa em ambos os aparelhos é necessário apertar em "Pair" para parear, estabelecendo desta forma a conecção. Por último, para testar se está funcionando pode aperta a tecla "Alt" + "Botão Esquerdo do Mouse", no qual será emitido um ruído do aparelho Bluetooth Speaker.

#### 2.2.1 Vídeo de Conectando os aparelhos

https://user-images.githubusercontent.com/106887744/175618444-541bb06e-4e55-4582-a0c2-265e351c6b06.mp4

### 2.4 Observações

Na parte de "config" é possível rever várias informações importante para ver se você está parenado com o aparelho que deseja, isso é possível por meio do "MAC Adress" tanto de origem qaunto de destino" que é possível observar melhor na imagem abaixo.

#### 2.4.1 "Config" do Bluetooth Speaker

![som_config](https://user-images.githubusercontent.com/106887744/175625881-f2d034fd-7634-440b-912b-a16484083736.png)

#### 2.4.2 "Config" do Portable Music Player

![celular_config](https://user-images.githubusercontent.com/106887744/175626478-64ee6c0f-28f4-4e5a-9ace-bde97b20cd45.png)

