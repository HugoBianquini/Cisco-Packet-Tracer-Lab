# Criando Redes Wireless

Vamos lá!

## 1. Começando pelo início
Vamos primeiramente escolher nosso aparelho. Para este exemplo iremos usar um Roteador de rede de internet wireless (WRT300N). <br/>
![roteador](https://user-images.githubusercontent.com/31890192/175184102-b92a3477-fe2e-4e84-85ba-9393c3762b8f.png)
<br/>

## 2. Configurando a Rede
Para a configuração da rede iremos usar a interface gráfica do aparelho. Basta inserir os dados da rede desejados como os exemplos abaixo.

### 2.1. Identificação da Rede
![trab2](https://user-images.githubusercontent.com/31890192/175184844-c696b495-77c1-4a3a-8bb8-a413bc0768f2.png)

### 2.2. Segurança da Rede
![trab3](https://user-images.githubusercontent.com/31890192/175184848-1fcdcd1e-e922-40f6-b8d7-753ca280e921.png)

## 3. Ingressando Aparelhos na Rede
Agora que a rede está configurada, iremos incluir os usuários desta rede. Para exemplo iremos imaginar que seja uma rede de um usuário que possua 1 Laptop e 1 Smartphone. <br/>
![trab4](https://user-images.githubusercontent.com/31890192/175185827-1081a88a-1176-407a-95cd-802f5415c02b.png)

## 4. Configurando Aparelhos
Para configurar os aparelhos, iremos utilizar a GUI do Laptop e configuração "bruta" do smartphone (pois o CPT não disponibiliza GUI para este aparelho).

### 4.1. Configurando Laptop
A conexão com a rede pelo Laptop será feita de forma simples seguindo os passos da interface gráfica (PC Wireless). <br/>
![trab5](https://user-images.githubusercontent.com/31890192/175187610-f4101eb6-b7e1-4c2f-ad67-b48e33789b73.png)

#### 4.1.1. Encontrando Rede
Basta clicar em "Refresh" e aguardar um sinal da rede.<br/>
![trab6](https://user-images.githubusercontent.com/31890192/175186965-0fe25654-6f5b-452f-bce6-5e4643c12d1c.png)

#### 4.1.2. Inserindo dados da Rede
![trab12](https://user-images.githubusercontent.com/31890192/175187718-23b50ef5-792f-48ec-bce0-f9ad6dc2650e.png)

#### 4.1.3. Checando conexão
Podemos observar a qual roteador o aparelho está conectado olhando a linha de conexão que é demonstrada na aplicação. <br/>
![trab7](https://user-images.githubusercontent.com/31890192/175186969-b47d700e-9f3a-4414-bbdd-99211f0e75a1.png)

### 4.2 Configurando Smartphone
Como a aplicação não fornece GUI para aparelhos Smartphone, usaremos a configuração padrão do CPT neste caso.<br/>

#### 4.2.1 Inserindo dados da Rede
Teremos que inserir os dados de rede com fidelidade ao que foi designado no aparelho.<br/>
![trab8](https://user-images.githubusercontent.com/31890192/175188134-5cea239b-726a-49d7-98ca-07a9b4620002.png)


#### 4.2.2 Checando conexão
Feito isso podemos notar que o aparelho Smartphone fora conectado a rede.<br/>
![trab9](https://user-images.githubusercontent.com/31890192/175188108-2c7cbe62-6f43-475d-b811-4bb2f3e77e26.png)

## 5. Verificando funcionalidade
Para conseguirmos checar a funcionalidade da rede, precisaremos dos endereços IP dos aparelhos. Como de costume, uma rede Wireless utiliza protocolo DHCP para
configuração dinâmica do endereço de seus usuários. <br/>
![trab10](https://user-images.githubusercontent.com/31890192/175188460-26e0c07c-ce9f-4cbc-906a-486502ea6470.png)<br/>
Podemos observar que em nosso roteador o range de endereços vai de 100 a 149, neste caso, podemos logicamente determinar os endereços do Laptop sendo como 100
e do Smartphone sendo como 101 por suas entradas na rede.<br/>
O próximo passo é utilizarmos o protocolo ICMP para troca de mensagens entre os aparelhos.<br/>

#### 5.1 Exemplo 1
![trab11](https://user-images.githubusercontent.com/31890192/175188802-a935d0a5-58ae-4650-8ed9-97d848f9a109.png)

#### 5.2 Exemplo 2
