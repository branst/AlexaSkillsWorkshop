# Taller Alexa Skills
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />


Con las Skills de Alexa Self-Hosted, podemos construir, editar, y publicar una skill desde la consola de Alexa de manera sencilla.
Alexa Skills incluye un editor de código para editar, manejar y hacer deploy de tus skills.
Para mas detalles de lo que Alexa self-hosted puede hacer, abrir [esta pagina](https://developer.amazon.com/docs/hosted-skills/build-a-skill-end-to-end-using-an-alexa-hosted-skill.html).

## Crear una Skill y cargar un modelo
1.  **Ir a [Amazon Developer Portal](http://developer.amazon.com/alexa?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Survey&sc_detail=fact-nodejs-V2_GUI-1&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Survey_fact-nodejs-V2_GUI-1_Convert_WW_beginnersdevs&sc_segment=beginnersdevs).  Arriba a la derecha hacer click en "Sign In".**

![Sign In](img/1-create.1.1.png?raw=true "Sign In")

2.  Una vez loggeado, haz click en el link de **Skills**.

![Skills](img/1-create.2.1.png?raw=true "Skills")

3.  Seleccionar **Create Skill**

![Create Skill](img/1-create.3.1.png?raw=true "Create Skill")

4. Darle un nombre a tu Skill. Este será el nombre con el cual los usuarios identificarán tu skill.

5. Elegir Spanish-MX.

![Create Skill](img/1-create.5.1.png?raw=true "Create Skill")

6. Deja el modelo **Custom** seleccionado. Elige **Alexa-Hosted** como método para hospedar tu Alexa Skill.

![Create Skill](img/1-create.7.1.png?raw=true "Create Skill")

7. Selecciona **Create Skill**.

![Create Skill](img/1-create.7.2.png?raw=true "Create Skill")

8. **Crear el modelo de Interacción para tu Skill**
	1. En el menú de la izquiera selecciona la opción de **JSON Editor** dentro de **Interaction Model**. Reemplaza el contenido existente por el contenido del archivo [esp.json](/models/esp.json). Click en **Save Model**.

	![Create Skill](img/1-create.8.1.png?raw=true "Create Skill")

	![Create Skill](img/1-create.8.2.png?raw=true "Create Skill")

    2. Si quieres cambiar el nombre de invocación de tu Skill, selecciona **Invocation** y modifica el **Skill Invocation Name**. 

	![Create Skill](img/1-create.8.3.png?raw=true "Create Skill")

    3. Click en "Build Model".

	 

## Hacer deploy del código de la Skill

1.  Dentro de tu Skill hace click en la pestaña de "Code".
A tu izquierda deberías ver una carpeta y sus archivos, hacer click en **index.js** para abirlo. Este archivo es el código de tu Alexa Skill.

![Create Skill](img/2-deploy.1.png?raw=true "Create Skill")

2. Seleccionar todo el texto existente y borrarlo. Luego reemplazarlo por el código de [index.js](/code/index.js).

3. Hacer click en "Raw" y luego copiar el código. Regresar a la pantalla de Alexa Skills y pegar el contenido dentro del editor de texto.

![Create Skill](img/2-deploy.3.png?raw=true "Create Skill")

4. Repetir los mismos pasos para el archivo **package.json** Copiar los contenidos de [package.json](/code/package.json), y pegarlos en el archivo package.json de la Skill en el editor de texto dentro de la pestaña "Code".

![Create Skill](img/2-deploy.4.png?raw=true "Create Skill")

5. Hacer click en "Save" y luego hacer "Deploy".

![Create Skill](img/2-deploy.5.png?raw=true "Create Skill")


## Probando tu Alexa Skill

Hasta ahora hemos creado un modelo y hecho deploy del código. Tu Skill ya está lista para ser probada.

1. Accede al  **Alexa Simulator**, desde la pestaña de **Test** en el menú de navegacion superior. 

![Create Skill](img/3-test.1.png?raw=true "Create Skill")

2. Hay una opcion llamada "Skill testing is enabled in:", que tiene seleccionada la opcion "Off" alternarla a "Development".

3. Validar que la skill funcione correctamente, para ello, invoca tu skill desde el **Alexa Simulator**. Podes escribir o mantener seleccionado el ícono de micrófono y luego hablar

![Create Skill](img/3-test.3.png?raw=true "Create Skill")

	1. **Escribiendo** "Abrir" seguido del nombre de invocación antes elegido. Por ejemplo, "Abrir curiosidades del espacio".
	2. **Usando tu voz** selecciona y apreta el microfono y dí: "Abrir" seguido del nombre de invocacion de tu skill.
	3. **Si olvidaste el nombre de invocación** de tu skill, podes ir a la pestaña de **Build** y navegar a **Invocation** para revisarlo.
	

## Extras

### Agregar otro idioma

1.  Dentro de la skill ir al menú de Build. Una vez en él, seleccionar el drop de idioma donde dice "Spanish (MX)" y seleccionar "Language Settings".

2. Hacer click en "Add New Language" y luego agregar Ingles "(English-US)" y hacer click en "Save".

3. Volver al menú principal de "Build".	

4. Seleccionar el nuevo idioma en el selector: "English US".

5. Repetir los pasos para agregar el modelo en ingles:
	1. En el menú de la izquiera selecciona la opcion de **JSON Editor** dentro de **Interaction Model**. Reemplaza el contenido existente por el contenido en el archivo [eng.json](/models/eng.json). Click en **Save Model**.
    2. Si quieres cambiar el nombre de invocación de tu Skill, selecciona **Invocation** y modifica el **Skill Invocation Name**. 
    3. Click en "Build Model".
    
6. Ya podemos volver a la pestaña de Test y probar la Skill en el nuevo idioma.

### Multiples interacciones

1. Seleccionar la pestaña de "Code".
2. Localizar la linea de código (linea 27): `// .reprompt(requestAttributes.t('HELP_REPROMPT'))` y remover los '//'. Quedaria: `.reprompt(requestAttributes.t('HELP_REPROMPT'))`

Ahora vamos a poder interactuar con nuestra skill repetidas veces en la misma invocación.

### Audio customizado

1. Localizar la linea numero 187, en la pestaña "Code", que contiene un listado de datos.
2. Reemplazar `'Un año en Mercurio es de solo 88 días',` por: `'<amazon:effect name="whispered">Un año en Mercurio es de solo 88 días</amazon:effect>',`

Ahora Alexa nos va a susurrar las respuestas. Podemos modificar y agregar nuevas opciones.

### Agregar mensaje de bienvenida

Podemos hacer que Alexa nos lea un mensaje de bienvenida cada vez que invocamos nuestra Skill para ello:

1. Ir a la pestaña de "Code" y reemplazar todo el código por el que esta ubicado aquí [indexFinished.js](/code/indexFinished.js).
2. Hacer click en "Save" y "Deploy".
3. Ir a la pestaña de "Test". Ahora podemos invocar la Skill y vamos a recibir el mensaje de bienvenida. Una vez recibido el mensaje, le podemos pedir una curiosidad, luego podremos volver a realizar la misma accion u otras.

### Integrar con servicios de terceros

Podemos hacer que Alexa se integre con otros sitios, por ejemplo, el precios de acciones:

1. Ir a la pestaña de "Code" y reemplazar el código, ubicar la linea número 6 `const apiKey = "";` y reemplazar las "" por: "DbSIOfP15LxoI7Z3IVxXOC2OcK6cakNwucHmPsqQ4DeOxVaMOa4AmojRd4y5"
2. Hacer click en "Save" y "Deploy".
3. Ir a la pestaña de "Test". Ahora podemos invocar la Skill y vamos a recibir el mensaje de bienvenida. Una vez recibido el mensaje, le vamos a poder solicitar el precios de las acciones, diciendo 'dime el precio de mis acciones'.






