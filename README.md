# Taller Alexa Skills
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />


Con una skill de Alexa Self-Hosted, podes construir, editar, y publicar una skill desde la consola de Alexa.
Alexa Skills incluye un editor de codigo para editar, manejar y hacer deploy de tus skills.
Para mas detallse de lo que Alexa self-hosted otorga, abrir [esta pagina](https://developer.amazon.com/docs/hosted-skills/build-a-skill-end-to-end-using-an-alexa-hosted-skill.html) en una nueva pestaña.

### Pasos para crear una Skill y cargar un modelo
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
    

### Hacer deploy del codigo de la Skill

1.  Adentro de tu Skill hace click en la pestaña de Codigo.
Deberias ver a la izquiera una carpeta y sus archivos, hacer click en **index.js** para abirlo. Este archivo es el codigo de tu Alexa Skill.

2. Seleccionar todo el texto existente y borrarlo. Luego reemplazar por el codigo de [index.js](index.js) dentro de este proyecto.

4. Hacer click en "Raw" y luego copiar el codigo. Regresar a la pantalla de Alexa Skills y pegar el contenido dentro del editor de texto.

5. Repetir los mismos pasos para el archivo **package.json** Copiar los contenidos de [package.json](package.json), y pegarlos en el archivo package.json de la Skill.

6. Hacer click en Save y luego hacer Deploy.


## Testing tu Alexa Skill

Hasta ahora hemos creado un modelo y hecho deploy del codigo. Tu Skill ya esta lista para ser probada.

1. Accede al  **Alexa Simulator**, desde la pestaña de **Test** en el menu de navegacion superior. 

2. Hay una opcion llamada "Skill testing is enabled in:", que tiene seleccionada la opcion 'Off' alternarla a 'Development'.

3. Validar que la skill funcione correctamente, invoca tu skill desde el **Alexa Simulator**. Podes escribir o mantener seleccionado el icono de microfono y luego hablar
	1. **Escribe** "Abrir" seguido del nombre de invocacion antes elegido. Por ejemplo, "Abrir curiosidades del espacio".
	2. **Usando tu voz** selecciona y apreta el microfono y di: "Abrir" seguido del nombre de invocacion de tu skill.
	3. **Si olvidaste el nombre de invocacion** de tu skill, podes ir a la pestaña de **Build** py navegar a **Invocation** para revisarlo.

