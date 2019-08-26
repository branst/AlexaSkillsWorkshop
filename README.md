# Taller Alexa Skills
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />


Con una skill de Alexa Self-Hosted, podes construir, editar, y publicar una skill desde la consola de Alexa.
Alexa Skills incluye un editor de codigo para editar, manejar y hacer deploy de tus skills.
Para mas detallse de lo que Alexa self-hosted otorga, abrir [esta pagina](https://developer.amazon.com/docs/hosted-skills/build-a-skill-end-to-end-using-an-alexa-hosted-skill.html) en una nueva pestaña.

## Crear una Skill y cargar un modelo
1.  **Ir a [Amazon Developer Portal](http://developer.amazon.com/alexa?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Survey&sc_detail=fact-nodejs-V2_GUI-1&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Survey_fact-nodejs-V2_GUI-1_Convert_WW_beginnersdevs&sc_segment=beginnersdevs).  Arriba a la derecha hacer click en "Sign In".**

2.  Una vez loggeado, haz click en el link de **Skills**.

3.   Seleccionar **Crear Skill**

4. Darle un nombre a tu Skill. Este sera el nombre con el cual los usuarios identificaran tu skill.

5. Elegir Español-MX.

6. Deja el modelo **Custom** seleccionado.

7. Elije **Alexa-Hosted** como metodo para alojar tu Alexa Skill.  Selecciona **Crear Skill**.

8. **Crear el modelo de Interaccion para tu Skill**
	1. En el menu de la izquiera selecciona la opcion de **JSON Editor** dentro de **Interaction Model**. Reemplaza el contenido existente por el contenido en el archivo [esp.json](/models/esp.json). Click en **Save Model**.
    2. Si quieres cambiar el nombre de invocacion de tu Skill, selecciona **Invocation** y modifica el **Skill Invocation Name**. 
    3. Click en "Build Model".
    

## Hacer deploy del codigo de la Skill

1.  Adentro de tu Skill hace click en la pestaña de Codigo.
Deberias ver a la izquiera una carpeta y sus archivos, hacer click en **index.js** para abirlo. Este archivo es el codigo de tu Alexa Skill.

2. Seleccionar todo el texto existente y borrarlo. Luego reemplazar por el codigo de [index.js](index.js) dentro de este proyecto.

4. Hacer click en "Raw" y luego copiar el codigo. Regresar a la pantalla de Alexa Skills y pegar el contenido dentro del editor de texto.

5. Repetir los mismos pasos para el archivo **package.json** Copiar los contenidos de [package.json](package.json), y pegarlos en el archivo package.json de la Skill.

6. Hacer click en Save y luego hacer Deploy.


## Probando tu Alexa Skill

Hasta ahora hemos creado un modelo y hecho deploy del codigo. Tu Skill ya esta lista para ser probada.

1. Accede al  **Alexa Simulator**, desde la pestaña de **Test** en el menu de navegacion superior. 

2. Hay una opcion llamada "Skill testing is enabled in:", que tiene seleccionada la opcion 'Off' alternarla a 'Development'.

3. Validar que la skill funcione correctamente, invoca tu skill desde el **Alexa Simulator**. Podes escribir o mantener seleccionado el icono de microfono y luego hablar
	1. **Escribe** "Abrir" seguido del nombre de invocacion antes elegido. Por ejemplo, "Abrir curiosidades del espacio".
	2. **Usando tu voz** selecciona y apreta el microfono y di: "Abrir" seguido del nombre de invocacion de tu skill.
	3. **Si olvidaste el nombre de invocacion** de tu skill, podes ir a la pestaña de **Build** py navegar a **Invocation** para revisarlo.
	

## Agregar otro idioma

1.  Dentro de la skill ir al menu de Build. Una vez en el seleccionar el drop de idioma donde dice 'Spanish (MX)' y seleccionar 'Language Settings'.

2. Hacer click en 'Add new language' y luego agregar Ingles (English-US) y hacer click en 'Save'.

3. Volver al menu principal de 'Build'

4. Seleccionar el nuevo idioma en el selector: 'English US'.

5. Repetir los pasos para agregar el modelo en ingles:
	1. En el menu de la izquiera selecciona la opcion de **JSON Editor** dentro de **Interaction Model**. Reemplaza el contenido existente por el contenido en el archivo [eng.json](/models/eng.json). Click en **Save Model**.
    2. Si quieres cambiar el nombre de invocacion de tu Skill, selecciona **Invocation** y modifica el **Skill Invocation Name**. 
    3. Click en "Build Model".
    
6. Ya podemos volver a la pestaña de Test y probar la Skill en el nuevo idioma.


## Modificar el código

### Multiples interacciones

1. Seleccionar la pestaña de 'Code'.
2. Localizar la linea de codigo (linea 44): `// .reprompt(requestAttributes.t('HELP_REPROMPT'))` y remover los '//'. Quedaria: `.reprompt(requestAttributes.t('HELP_REPROMPT'))`

Ahora vamos a poder volver a interactuar con nuestra skill repetidas veces.

### Audio customizado

1. Localizar la linea numero 262 que contiene un listado de datos.
2. Reemplazar `'Un año en Mercurio es de solo 88 días',` por: `'<amazon:effect name="whispered">Un año en Mercurio es de solo 88 días</amazon:effect>',`

Ahora Alexa nos va a susurrar las respuestas. Podemos modificar y agregar nuevas opciones.

### Agregar mensaje de bienvenida

Podemos hacer que Alexa nos de un mensaje de bienvenida cada vez que invocamos nuestra Skill para ello:

1. Ir a la pestaña de codigo y reemplazar todo el codigo por el que esta ubicado aqui [indexFinished.js](indexFinished.js).
2. Hacer click en Save y Deploy.
3. Ir a la pestaña de Test. Ahora podemos invocar la Skill y vamos a recibir el mensaje de bienvenida. Una vez recibido el mensaje, le podemos pedir una curiosidad.






