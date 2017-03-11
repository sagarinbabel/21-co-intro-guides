**Apresentamos-lhe a 21**
-----
Este guia introdutório irá ensinar-lhe o básico de 21.

* Instalando 21
* Usando 21 como um aplicativo
* Usando o mercado 21
* Configurando seu perfil 21
* Escrever programas com a biblioteca 21


**Introdução a 21**
-----
No início era a World Wide Web, construída em HTML. Então veio a Social Web, construída sobre a personalização. Mas acreditamos que existe uma terceira web ainda a ser construída: a Web Machine-Payable, construída com o Bitcoin.

Os tecnólogos têm desejado uma Web Machine-Payable por algum tempo. De fato, durante 20 anos, a especificação HTTP oficial incluiu um código para esse fim, marcado especificamente para uso futuro: 402 - Pagamento necessário.

Com 21, fizemos o nosso melhor para ajudar a trazer esse futuro.

21 é um software livre que implementa o código de status HTTP exigido pelo pagamento e muito mais. Facilita (a) enviar e receber micropagamentos através de HTTP e (b) escrever novos tipos de programas que usam essa tecnologia básica como um primitivo intrínseco, como APIs pagáveis a máquina e agentes inteligentes.

Se esses conceitos lhe interessam, e se a idéia de uma terceira web baseada em micropagamentos de máquina a máquina é excitante, pode valer a pena seu tempo para aprender 21. Vamos começar.

Visão geral
----
Este guia quickstart irá apresentá-lo às capacidades de 21, software livre que torna mais fácil de forma programática comprar e vender produtos digitais para bitcoin. Você pode pensar em 21 de quatro maneiras diferentes:

***App***: A maneira mais simples de entender 21 é como um aplicativo de linha de comando que você pode instalar rapidamente em qualquer dispositivo para obter bitcoin em uma variedade de maneiras.

***Marketplace***: A próxima maneira de entender 21 é como um mercado que permite que você troque chamadas de API (e, portanto, recursos de máquina) para bitcoin. Você pode visualizar o diretório de chamadas de API disponível para venda em 21.co/mkt, e você pode usar o 21 para publicar suas próprias APIs pagáveis ​​por máquina com algumas teclas digitadas.

***Network***: A terceira maneira de entender 21 é como uma espécie de "rede capitalista", onde você pode monitorar os ganhos de suas várias máquinas e encontrar outros desenvolvedores que estão construindo serviços a pagar por máquinas.

***Library***: A maneira final de entender 21 é como uma biblioteca Python 3 chamada two1, que permite que você crie seus próprios aplicativos personalizados pagos por máquina. Com two1, você pode adicionar micropagamentos a serviços da Web novos ou existentes com uma linha de código.

À medida que cada uma destas peças interage com as outras, a melhor maneira de compreendê-las é aprender fazendo. Então vamos começar instalando 21, e depois explorar cada um desses quatro aspectos por sua vez.

Antes de prosseguir, observe que 21 está atualmente em versão beta, e alguns dos comandos (especialmente 21 vendem) envolvem a execução de um servidor localmente. Enquanto nos esforçamos para estar conscientes da segurança, é melhor durante a fase beta instalar 21 em um computador Bitcoin 21, um computador Bitcoin DIY, uma máquina virtual Amazon, um computador antigo ou algum outro dispositivo autônomo que não é o seu laptop pessoal principal.

**Instalação**
----

21 é atualmente suportado no Ubuntu Linux 14.04 executado em Amazon AWS e Mac OS X 10.7+. A maioria das funções também são suportadas em outras plataformas baseadas em Debian, como 21 Bitcoin Computers ou DIY Bitcoin Computers. O suporte para outras plataformas está disponível em breve.

A instalação é simples. Basta digitar isso na linha de comando:

`curl https://21.co | sh`

Sinta-se livre para visualizar o script antes da instalação. Observe que o uso de `https` é obrigatório aqui. Depois de instalar o script, visite a página de inscrição para criar sua conta.

***21 login: Faça login em sua conta 21***
----

Depois de instalar 21 e configurar sua conta 21, você pode efetuar login na sua conta na linha de comando da seguinte maneira:

`21 login`

Aqui está o que parece:

> `You do not have a Bitcoin wallet configured. Let's create one. Press any key ...
> 
> Wallet successfully created.
> 
> You can recover the private key to your wallet using the following 12 words (in this order) :
> 
> champion hotel review lake toaster immense picnic soldier glimpse candy girl side
> 
> Write down and store these words in a safe place.
> 
> Press any key ...
> 
> If you don't have a 21 account, visit https://21.co/signup to create one. 
> 
> Username: harding4
> Password (Typing will be hidden): 
> logging in harding4
> Setting default payout address to: 115kjVQznK4Skp8z9TYKanWgLU5oQXS1Bp
> Check out our introductory guide to learn the basics of 21: https://21.co/learn/intro-to-21/`


Conforme mostrado, você será solicitado a criar uma carteira Bitcoin. Siga as instruções e certifique-se de gravar o mnemônico fornecido a você. Esta é a cópia de segurança para o acesso à sua carteira. Por favor, note que 21 não pode ajudá-lo a restaurar sua carteira Bitcoin se você perder o mnemônico.

Em seguida, você será solicitado a digitar o nome de usuário 21 que você acabou de criar juntamente com sua senha 21. Antes de prosseguir, recomendamos que a senha do sistema fique segura, executando o `passwd` se você ainda não o tiver feito (sua senha do sistema é diferente da sua senha).

****21 Market: Junte-se a um mercado privado virtual****

**Nota:** esta seção se aplica somente aos usuários do 21 Bitcoin Computer, Docker virtualizado e Amazon EC2.

Quando um novo dispositivo se conecta à Internet, ele normalmente atua como um cliente, ou seja, algo que pode iniciar conexões a domínios como google.com para baixar informações. No entanto, o software 21 também permite que sua máquina atue como um servidor que vende recursos de máquina-pagáveis para bitcoin. Para fazer isso, ele precisa permitir que outras máquinas possam enviar pacotes para sua máquina para solicitar bens digitais sem conhecer o endereço IP ou nome de domínio específico da máquina com antecedência.

Execute o seguinte comando para ingressar na rede:

`21 market join`

Aqui está o que parece:

> WARNING
> 
> Note that the 21 Network operates very similarly to a public Wi-Fi
> access point, and carries with it the same security risks as a public
> "hotspot" that allows each device to connect to all other devices on the
> same network.  By executing this command to join the 21 Network, you make
> it possible for others to directly connect to your device.  In addition
> to being able to buy your digital goods for bitcoin, they will be able
> to access other services shared by your device such as shared folders
> (including Dropbox and Time Capsule folders) and streaming media (such
> as provided by iTunes).  Accordingly, you may also see services shared
> by other users.
> 
> Please remember that the 21 software is in beta and not ready for
> commercial release.  WE ARE PROVIDING THE 21 SOFTWARE AS-IS, AND YOU
> ASSUME ALL RISK OF USING 21 WHILE IN BETA.
> 
> To help protect the security of your systems when using 21 while in
> beta, we recommend you running the software on an EC2 instance, an old
> laptop that doesn't provide any shared resources, or a small standalone
> machine such as a 21 Bitcoin Computer (21.co/buy) or DIY Bitcoin Computer
> (21.co/diy).
> 
> Network: 21mkt
> 
> I understand and wish to continue [y/n]: y
> You might need to enter your superuser password.
> Joined network 21market. It may take a few seconds for joining to take effect.
> Run 21 market status to verify you have successfully joined.

Esse comando faz com que sua máquina ingressar em um mercado privado virtual onde outros computadores na rede podem comprar e vender arquivos diretamente com você. Conforme mostrado, o comando irá alertá-lo sobre os riscos de ingressar na rede e informá-lo de que pode precisar de permissões de superusuário para executar. Se não imprimir outras mensagens de erro, isso significa que você entrou na rede com êxito, o que você pode confirmar executando o `21 market status`

**Nota**: Após a execução do mercado 21, a máquina estará em uma rede privada com um IP virtual. A principal diferença da internet é que cada IP virtual nesta rede está funcionando 21 e, portanto, tem uma carteira bitcoin mais a capacidade de comprar e vender produtos digitais para bitcoin. Seria bom se todos os outros computadores nesta rede fossem amigáveis, mas não podemos garantir isso. Durante o período beta, executar 21 em um dispositivo autônomo como uma VM ou um computador Bitcoin 21 irá fornecer um nível adicional de segurança.

****21 doctor: Teste sua 21 instalação****
----

Agora você pode testar que sua instalação é totalmente funcional executando o seguinte comando:

`21 doctor`

Aqui está o que parece:

> 21 doctor
> 
> Checking health..
> 
> 
> Checking general settings..
> 
>   IP Address                         ->  10.137.2.13                          [PASS]
>   Operating System                   ->  Linux                                [PASS]
>   Operating System Release Version   ->  4.1.13-9.pvops.qubes.x86_64          [PASS]
>   Python Version                     ->  3.4.2                                [PASS]
>   21 Tool Version                    ->  3.3.0                                [PASS]
> 
> 5/5 Checks passed, 0 failed, 0 warnings, and 0 skipped
> 
> Checking dependencies..
> 
>   Two1 CLI                           ->  /home/user/dotco/jupyter/venv/bi...  [PASS]
>   Two1 Dotenv                        ->  /home/user/.two1/two1.json           [PASS]
>   Two1 Library                       ->  /home/user/dotco/jupyter/venv/li...  [PASS]
>   Two1 Wallet                        ->  /home/user/dotco/jupyter/venv/bi...  [PASS]
>   Zerotier CLI                       ->  /usr/bin/zerotier-cli                [PASS]
> 
> 5/5 Checks passed, 0 failed, 0 warnings, and 0 skipped
> 
> Checking servers..
> 
>   21 API                             ->  https://api.21.co                    [PASS]
>   21 Logging                         ->  https://logger.21.co                 [PASS]
>   21 Pool                            ->  swirl+tcp://grid.21.co:21006         [PASS]
>   21 Blockchain Provider             ->  https://blockchain.21.co             [PASS]
>   21 Pypicloud                       ->  https://pypi-3844.21.co              [PASS]
>   21 Slack                           ->  https://slack.21.co                  [PASS]
>   21 Marketplace                     ->  https://21.co/mkt                    [PASS]
>   21 Website                         ->  https://21.co                        [PASS]
> 
> 8/8 Checks passed, 0 failed, 0 warnings, and 0 skipped
> 
> Summary
> 
> 18/18 Checks passed, 0 failed, 0 warnings, and 0 skipped


Conforme mostrado, o comando imprimirá um relatório de status que confirma que tudo está funcionando corretamente ou então fornece uma lista de erros que precisam ser corrigidos. Se você tentou resolver esses erros e precisar de ajuda para sua instalação, não hesite em ir [ao nosso canal Slack.](https://slack.21.co/)