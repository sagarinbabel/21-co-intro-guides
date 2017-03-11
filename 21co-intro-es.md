**Les presentamos a 21**
-------

Esta guía le enseñará los fundamentos de 21.

* Instalación de 21
* Uso de 21 como aplicación
* Uso del mercado 21
* Configuración de su perfil 21
* Escribir programas con la biblioteca 21

**Introducción a 21**
---------

En el principio era la World Wide Web, construida sobre HTML. Luego vino la Red Social, basada en la personalización. Pero creemos que hay una tercera web todavía por construir: la Web de Máquina-Pagable, basada en Bitcoin.

Los tecnólogos han deseado una Web de máquina pagada por bastante tiempo. De hecho, durante 20 años la especificación HTTP oficial ha incluido un código para este propósito, marcado específicamente para uso futuro: 402 - Pago Requerido.

Con 21, hemos hecho todo lo posible para ayudar a traer ese futuro.

21 es un software libre que implementa el código de estado HTTP de pago requerido y mucho más. Facilita (a) enviar y recibir micropagos a través de HTTP y (b) escribir nuevos tipos de programas que usan esta tecnología básica como una primitiva intrínseca, como las API a máquina y los agentes inteligentes.

Si estos conceptos le interesan, y si la idea de una tercera web basada en micropagos de máquina a máquina es emocionante, puede valer la pena su tiempo para aprender 21. Empecemos.

**Visión de conjunto**
---------

Esta guía rápida le presentará a las capacidades de 21, software libre que hace que sea fácil de forma programática comprar y vender productos digitales para bitcoin. Se puede pensar en 21 de cuatro maneras diferentes:

***App***: La forma más simple de entender 21 es como una aplicación de línea de comandos que puede instalar rápidamente en cualquier dispositivo para obtener bitcoin de una variedad de maneras.

***Mercado***: La siguiente manera de entender 21 es como un mercado que le permite intercambiar llamadas API (y por lo tanto recursos de la máquina) para bitcoin. Puede ver el directorio de llamadas API disponible para la venta en 21.co/mkt, y puede usar 21 para publicar sus propias API de pago por máquina con unas pocas teclas.

***Red***: La tercera forma de entender 21 es como una especie de "red capitalista", donde puede monitorear las ganancias de sus varias máquinas y encontrar otros desarrolladores que están construyendo servicios a máquina.

***Biblioteca***: La última manera de entender 21 es como una biblioteca de Python 3 llamada two1, que le permite construir sus propias aplicaciones personalizadas a máquina. Con two1 puede agregar micropagos a servicios web nuevos o existentes con una línea de código.

A medida que cada una de estas piezas interactúa con las otras, la mejor manera de entenderlas es aprender haciendo. Así que vamos a empezar por la instalación de 21, y luego explorar cada uno de estos cuatro aspectos a su vez.

  Antes de proceder, tenga en cuenta que 21 está actualmente en versión beta y algunos de los comandos (especialmente 21 venta) implican ejecutar un servidor localmente. Mientras nos esforzamos por ser conscientes de la seguridad, es mejor durante la fase beta instalar 21 en una Computadora Bitcoin, una Computadora Bitcoin de DIY, una Máquina Virtual de Amazon, una computadora vieja o algún otro dispositivo independiente que no sea su computadora personal principal.

**Instalación**
-----

21 es actualmente compatible con Ubuntu Linux 14.04 ejecutado en Amazon AWS y Mac OS X 10.7+. La mayoría de las funciones también son compatibles con otras plataformas basadas en Debian, como 21 Bitcoin Computers o DIY Bitcoin Computers. Pronto estará disponible el soporte para otras plataformas.

La instalación es simple. Simplemente escriba esto en la línea de comandos:

`curl https://21.co | sh`

Siéntase libre de previsualizar el script antes de la instalación. Tenga en cuenta que el uso de https es obligatorio aquí. Una vez que haya instalado el script, visite la página de registro para crear su cuenta.

***21 inicio de sesión: Inicie sesión en su cuenta***
---

Una vez que haya instalado 21 y configurado su cuenta 21, puede iniciar sesión en su cuenta en la línea de comandos de la siguiente manera:

`21 login`

Esto es lo que aparece:

> You do not have a Bitcoin wallet configured. Let's create one. Press any key ...
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
> Check out our introductory guide to learn the basics of 21: https://21.co/learn/intro-to-21/

Como se muestra, primero se le pedirá que cree una cartera Bitcoin. Siga las instrucciones y asegúrese de grabar el mnemotécnico que se le proporciona. Esta es la copia de seguridad para el acceso a su cartera. Tenga en cuenta que 21 no puede ayudarle a restaurar su cartera Bitcoin si pierde el mnemónico.

A continuación, se le pedirá que introduzca el nombre de usuario 21 que acaba de crear junto con su contraseña. Antes de proceder, recomendamos que su contraseña del sistema sea segura ejecutando `passwd` si aún no lo ha hecho (su contraseña del sistema es distinta de su contraseña).

***21 market: Únase a un mercado privado virtual***
----------------

Nota: esta sección sólo se aplica a los usuarios de la computadora 21 Bitcoin, Docker virtualizado y Amazon EC2.

Cuando un nuevo dispositivo se conecta a Internet, normalmente actúa como un cliente, es decir, algo que puede iniciar conexiones a dominios como google.com para descargar información. Sin embargo, el software 21 también permite que su máquina actúe como un servidor que vende recursos de pago por máquina para bitcoin. Para ello, debe permitir que otras máquinas puedan enviar paquetes a su máquina para solicitar bienes digitales sin conocer previamente la dirección IP o el nombre de dominio específico de la máquina.

Ejecute el siguiente comando para unirse a la red:

`21 market join`

Su salida se ve así:

> WARNING
> -------
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

Este comando hace que su máquina se una a un mercado privado virtual donde otros equipos de la red pueden comprar y vender archivos directamente con usted. Como se muestra, el comando le avisará acerca de los riesgos de unirse a la red e informará de que puede necesitar permisos de superusuario para ejecutarse. Si no imprime ningún otro mensaje de error, significa que se ha unido correctamente a la red, lo que puede confirmar si ejecuta el `21 market status`

**Nota**: Después de ejecutar el 21 market, su máquina estará en una red privada con un IP virtual. La diferencia principal de Internet es que cada IP virtual en esta red está funcionando 21, y por lo tanto tiene una cartera bitcoin más la capacidad de comprar y vender productos digitales para bitcoin. Sería bueno si todas las otras computadoras de esta red fueran amigables, pero no podemos garantizarlo. Durante el período beta, ejecutar 21 en un dispositivo autónomo como una VM o un ordenador 21 Bitcoin proporcionará un nivel adicional de seguridad.

**21 doctor: Pruebe su instalación 21**
-------

Ahora puede probar que su instalación es completamente funcional ejecutando el siguiente comando

`21 doctor`

Su salida se ve así:

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

Como se muestra, el comando imprimirá un informe de estado que confirma que todo está funcionando correctamente, o bien proporciona una lista de errores que deben corregirse. Si ha intentado resolver estos errores y necesita ayuda con su instalación, no dude en ir [a nuestro canal Slack.](https://slack.21.co/)
