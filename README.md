
Esse é um tutorial que ira auxiliar na hora de conseguir desabilitar a placa dedicada AMD RadeonX3000, vejo diversos vídeos e tutoriais, mas todos eles em outras línguas, então hoje trago para vocês este em Português/brasil.

> Iniciamos desligando a maquina e dando um reset pelo SMC
Esse reset normalmente a tela da um flash de luz, mas se caso não acontecer com você, não se preocupe, segure por 5 segundos e já da certo

### ETAPA 1:
> Segure as seguintes teclas juntas:

```shell
Shift + ctrl + option(alt) + botão de energia
```
> Pode segurar pode 5 segundos apenas.

Logo em seguida, vamos dar um reset no NVRAM, esse reset acontece quando o mac liga e desliga duas vezes, ou seja, você vai ficar segurando esses botões até sua maquina ligar e desligar e ligar de novo até ela desligar de novo.

### ETAPA 2:
> Aperte junto as teclas:
```shell
Command + Option + P + R
```
> Até que ele se reinicie duas vezes

### ETAPA 3:
> Próximo passo, vai ser quando deixamos ele reiniciar segurando as teclas:
```shell
Command + R + S
```
Esse é o modo de recuperação único, se você usar o HIGH SIERRA só o comando: Command + S Já da certo
Quando iniciar o modo de recuperação único, você terá duas opções, a primeira é digitar:

### ETAPA 4:
```shell
csrutil disable
```
> Se o acesso for concedido pule para a ETAPA 7, se for negado, continue daqui o passo a passo.
### ETAPA 5:
> Digite:
```shell
nvram fa4ce28d-b62f-4c99-9cc3-6815686e30f9:gpu-power-prefs=%01%00%00%00 
```
> Aperte enter e depois:
```shell
nvram boot-args="-v" 
```
> Aperte enter novamente.
Agora vamos ter que ser rápidos e digitar:
```shell
Reboot 
```
> Aperte enter.
Rapidamente aperte as teclas
```shell
Command + R
```
> opção que funcionou comigo foi Command + Option + R

segure as teclas ate que o macbook entre em modo de recuperação pela internet, ele irá aparecer o globo terrestre e escrever que esta em modo recuperação pela internet.
Quando entrar no modo de recuperação, você terá que conectar a uma rede wifi ou ethernet para continuar, após isso aparecera uma tela onde você escolhera sua língua, ai só colocar Português/Brasil e apertar em continuar, entramos no modo de recuperação, no canto superior esquerdo você vera a opção Utilities(utilitários), aperte nele e escolha a opção Terminal.

### ETAPA 6:
> No terminal você digitara:
```shell
Csrutil disable 
```
E aperte enter, ele aparecera que a proteção do sistema foi desativada
Em seguida digite:
```shell
Reboot  
```
E novamente entramos em modo de recuperação único, segure as teclas enquanto o computador reinicia:
> Command + S

### ETAPA 7:
No modo recuperação único, vamos digitar novamente os comandos da etapa 5:
> Digite:
```shell
nvram fa4ce28d-b62f-4c99-9cc3-6815686e30f9:gpu-power-prefs=%01%00%00%00 
```
> Aperte enter e depois:
```shell
nvram boot-args="-v" 
```
> Aperte enter novamente.
Agora vamos ter que ser rápidos digite:
```shell
Reboot 
```
> Aperte enter.
Rapidamente aperte as teclas
```shell
Command + S
```
### ETAPA 8:
No modo de recuperacao único você digitara:
```shell
/sbin/mount -uw/ 
```
> E apertar enter
Em seguida digite:
```shell
mkdir -p /System/Library/Extensions-off 
```
> proximo comando:
```shell
mv /System/Library/Extensions/AMDRadeonX3000.kext  /System/Library/Extensions-off 
```
> apos digitar e apertar enter digite:
```shell
touch /System/Library/Extensions/ 
```
> vamos reiniciar ele com:
```shell
reboot 
```
> seguido com as teclas
> Command + S
### ETAPA 9:
No modo recuperacao digite:
```shell
sudo nvram boot-args=”” 
```
> de um reinicio na sua maquina seguido das teclas:
Command + R
> Ou Command + Option + R

Entraremos novamente no modo de recuperação via internet, então basta fazer os mesmos passos, selecione língua português/brasil depois vá até aba utilitários e abra terminal.
### ETAPA 10:
No terminal digite:
```shell
csrutil enable  
```
para ativarmos nossa proteção novamente
seguido de Reboot para reiniciarmos pela ultima vez nossa maquina e esta pronta para o uso normal, esse modo é possível usar as teclas F1 e F2 para ajustar o brilho da tela, mas não será mais possível usar ele com monitor externo.

Guias seguidos para esse tutorial:
[Post](https://gist.github.com/cdleon/d1eff7246a25193304284ecec40445b0)
[Video](https://www.youtube.com/watch?v=iLft4N54zvU)

> ajude doando Paypal: marcovoceali@gmail.com
