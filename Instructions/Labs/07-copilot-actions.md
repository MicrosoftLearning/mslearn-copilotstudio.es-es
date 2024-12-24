---
lab:
  title: Creación de acciones de Copilot
  module: Enhance Microsoft Copilot Studio copilots
---

# Creación de acciones de Copilot

## Escenario

En este laboratorio, aprenderás a:

- Creación de acciones de Copilot

## Aprendizaje

- Cómo agregar el uso de Power Automate para acceder a datos en Microsoft Dataverse

## Pasos de alto nivel del laboratorio

- Creación de un flujo de nube de Power Automate para recuperar datos de Dataverse con una acción de copiloto
- Creación de un flujo de nube de Power Automate para crear datos de Dataverse con una acción de copiloto
  
## Requisitos previos

- Debes haber completado el **Laboratorio: Trabajar con entidades**

## Pasos detallados

## Ejercicio 1: Creación de una acción de Copilot para recuperar datos de Dataverse

Microsoft Copilot Studio puede acceder a los datos de Microsoft Dataverse mediante flujos de nube de Power Automate.

### Tarea 1.1: Creación de un flujo de Power Automate para recuperar una propiedad

1. Ve al portal `https://copilotstudio.microsoft.com` de Microsoft Copilot Studio y asegúrate de que estás en el entorno adecuado.

1. Selecciona **Copilotos** en el panel de navegación izquierdo.

1. Selecciona el **servicio de reserva inmobiliaria** que creaste en el laboratorio anterior.

1. Seleccione la pestaña **Acciones**.

1. Selecciona **+ Agregar una acción**.

    ![Captura de pantalla del paso 1 de agregar una acción.](../media/add-action-step-1.png)

1. Selecciona el filtro **Flujo** y, a continuación, selecciona **Crear un nuevo flujo**.

1. Inicia sesión en Power Automate si se te solicita.

    ![Captura de pantalla del flujo de Power Automate con pasos de desencadenador y respuesta.](../media/create-flow-step1.png)

1. Selecciona **Ejecutar un flujo desde Copilot** en la parte superior izquierda de la pantalla y escribe `Get Property` como nombre del flujo.

1. Selecciona el paso de desencadenador **Ejecutar un flujo desde Copilot** y selecciona **+ Agregar una entrada**.

1. Seleccione **Texto**.

1. Escribe `Bedrooms` en **Entrada** y `Number of Bedrooms` para **Escribe la entrada**.

    ![Captura de pantalla de las propiedades del desencadenador del flujo.](../media/create-flow-step2.png)

1. Selecciona el icono **+** entre los dos pasos del flujo y selecciona **Agregar una acción**.

1. Escribe `Dataverse` en el campo **Buscar** y selecciona **Ver más** para el conector de **Microsoft Dataverse**.

    ![Captura de pantalla de la búsqueda de conector en el flujo.](../media/create-flow-step3.png)

1. Selecciona la acción **Listar filas**.

1. Si se te solicita autenticación, selecciona **OAuth** y selecciona **Iniciar sesión**.

    > **Nota:** si ves un error "**No se pudo crear la conexión de OAuth**", es posible que tengas que permitir elementos emergentes en tu explorador.

    ![Captura de pantalla del error de OAuth.](../media/failed-oauth-popup.png)

    ![Captura de pantalla de permitir elementos emergentes en Edge.](../media/failed-oauth-popup-2.png)

1. Selecciona **Propiedades inmobiliarias** para nombre de tabla.

1. Escribe `contoso_bedrooms eq ` (con un espacio después de **eq**) en el campo **Filtrar filas**.

1. Con el campo **Filtrar filas** aún seleccionado, selecciona el icono de **rayo** a su derecha y, a continuación, selecciona el parámetro **Bedrooms**.

    ![Captura de pantalla de la configuración de la acción listar filas.](../media/create-flow-step4.png)

1. En el panel principal de Power Automate, selecciona la acción **Responder a Copilot** y selecciona **+ Agregar una salida**.

1. Seleccione **Texto**.

1. Escribe `PropertyId` para **Escriba un nombre**

1. Selecciona el campo **Escribir un valor con el que responder** y selecciona **fx (Insertar expresión)**.

1. Escribe la siguiente expresión en el campo superior:

    ```
    first(outputs('List_rows')?['body/value'])['contoso_realestatepropertyid']
    ```

    ![Captura de pantalla de la configuración de la acción de respuesta.](../media/create-flow-step5.png)

1. Seleccione **Agregar**.

1. Seleccione **+Agregar una salida**.

1. Seleccione **Texto**.

1. Escribe `PropertyName` para **Escriba un nombre**.

1. Selecciona el campo **Escribir un valor con el que responder** y selecciona **fx (Insertar expresión)**.

1. Escriba la siguiente expresión:

    ```
    first(outputs('List_rows')?['body/value'])['contoso_propertyname']
    ```

1. Seleccione **Agregar**.

1. Selecciona la pestaña **Configuración** en el panel **Responder a Copilot**.

1. Asegúrate de que **Respuesta asincrónica** esté establecida en **Desactivado**.

    ![Captura de pantalla de la configuración de la acción de respuesta.](../media/create-flow-step6.png)

1. Selecciona **Guardar** junto a la parte superior derecha de la página.

1. Espera a que se guarde por completo y, a continuación, cierra la pestaña Power Automate.

### Tarea 1.2: Adición de una acción de Copilot para recuperar una propiedad

1. Selecciona **Actualizar** en el cuadro de diálogo Copilot Studio para ver el nuevo flujo.

1. Selecciona el flujo **Obtener propiedad**.

    ![Captura de pantalla del paso 1 de agregar una acción de flujo.](../media/add-action-flow-step-1.png)

1. Seleccione **Siguiente**.

1. Seleccione **Siguiente**.

1. Seleccione **Finalizar**.

### Tarea 1.3: Adición de la acción Obtener Copilot de propiedad al tema

1. Selecciona la pestaña **Temas**.

1. Selecciona el tema **Reservar una presentación inmobiliaria**.

1. Selecciona el icono **+** debajo del nodo **¿Cuántos dormitorios necesita?**, selecciona **Llamar a una acción** y, a continuación, selecciona el flujo **Obtener propiedad**.

    ![Captura de pantalla del paso 2 de agregar una acción de flujo.](../media/add-action-flow-step-2.png)

1. Selecciona la variable **NumberofBedrooms** para el parámetro de entrada **Bedrooms**.

    ![Captura de pantalla del paso 3 de agregar una acción de flujo.](../media/add-action-flow-step-3.png)

1. Selecciona los **tres puntos** en el nodo **¿Qué propiedad desea ver?** y selecciona **Eliminar**.

1. Selecciona el icono **+** en el nodo **Acción** y selecciona **Enviar un mensaje**.

1. En el campo **Escribe un mensaje**, escribe `Property ` (con un espacio después).

1. En el mismo nodo, selecciona el icono **{X} (Insertar variable)** y selecciona la variable **PropertyName**.

    ![Captura de pantalla del paso 4 de agregar una acción de flujo.](../media/add-action-flow-step-4.png)

1. Seleccione **Guardar**.

## Ejercicio 2: Creación de una acción de Copilot para crear datos en Dataverse

Microsoft Copilot Studio puede crear datos en Microsoft Dataverse mediante flujos de nube de Power Automate.

### Tarea 2.1: Creación de un flujo de Power Automate para realizar una reserva

1. Selecciona la pestaña **Acciones** en **Servicio de reserva inmobiliaria**.

1. Selecciona **+ Agregar una acción**.

1. Desplázate hacia abajo y selecciona **Crear un nuevo flujo**.

1. Selecciona **Ejecutar un flujo desde Copilot** en la parte superior izquierda de la pantalla y escribe `Create Booking Request` como nombre del flujo.

1. Selecciona el paso de desencadenador **Ejecutar un flujo desde Copilot** y selecciona **+ Agregar una entrada**.

1. Seleccione **Texto**.

1. Escribe `PropertyId` en **Entrada** y `Property` para **Escriba su entrada**.

1. Seleccione **+ Agregar una entrada**.

1. Seleccione **Texto**.

1. Escribe `ViewerName` para **Entrada** y `Viewer Name` en **Escriba su entrada**.

1. Seleccione **+ Agregar una entrada**.

1. Seleccione **Texto**.

1. Escribe `ViewerEmail` para **Entrada** y `Viewer Email` para **Escriba su entrada**.

    ![Captura de pantalla de la configuración de la acción parámetros de flujo.](../media/create-flow2-step1.png)

1. Selecciona el icono **+** entre los dos pasos del flujo y selecciona **Agregar una acción**.

1. Escribe `Dataverse` en el campo **Buscar** y selecciona **Ver más** para el conector de **Microsoft Dataverse**.

1. Selecciona la acción **Agregar una nueva fila**.

1. Selecciona **Solicitudes de reserva** para el nombre de tabla.

1. Escribe `Copilot booking` en el campo **Nombre de reserva**.

1. Seleccione **Mostrar todo** en **Parámetros avanzados**.

1. Escribe `contoso_bookingrequests()` en el campo **Propiedad (Propiedades inmobiliarias)**, mueve el cursor dentro del paréntesis, selecciona el icono de **rayo** y, a continuación, selecciona el parámetro **PropertyId**.

1. Selecciona el campo **Correo electrónico del visor**, selecciona el icono de **rayo** y, a continuación, selecciona el parámetro **ViewerEmail**.

1. Selecciona el campo **Nombre del visor**, selecciona el icono de **rayo** y, a continuación, selecciona el parámetro **ViewerName**.

    ![Captura de pantalla de la configuración de la acción agregar fila de flujo.](../media/create-flow2-step2.png)

1. Selecciona la acción **Responder a Copilot**.

1. Seleccione la pestaña **Configuración**.

1. Asegúrate de que **Respuesta asincrónica** esté establecida en **Desactivado**.

1. Selecciona **Guardar** en la parte superior derecha de la ventana.

1. Espera a que se guarde por completo y, a continuación, cierra la pestaña Power Automate.

### Tarea 2.2: Adición de una acción de Copilot para crear una solicitud de reserva

1. Selecciona **Actualizar** en el cuadro de diálogo Copilot Studio para ver el nuevo flujo.

1. Selecciona el flujo **Crear solicitud de reserva**.

1. Seleccione **Siguiente**.

1. Seleccione **Siguiente**.

1. Seleccione **Finalizar**.

### Tarea 2.3: Adición de la acción de Copilot Crear solicitud de reserva al tema

1. Selecciona la pestaña **Temas**.

1. Selecciona el tema **Reservar una presentación inmobiliaria**.

1. Selecciona el icono **+** debajo del nodo **¿En qué fecha y hora desea ver la propiedad?**, selecciona **Llamar a una acción** y, a continuación, selecciona el flujo **Crear solicitud de reserva**.

1. Selecciona la variable **PropertyId** para el parámetro de entrada **PropertyId**.

1. Selecciona la variable **Name** para el parámetro de entrada **ViewerName**.

1. Selecciona la variable **EmailAddress** para el parámetro de entrada **ViewerEmail**.

1. Selecciona el icono **+** situado debajo del nuevo nodo **Acción**, selecciona **Administración de temas**, selecciona **Ir a otro tema** y selecciona **Finalizar conversación**.

1. Seleccione **Guardar**.

1. Selecciona **Publicar** y vuelve a seleccionar **Publicar**.

## Ejercicio 3: Prueba de las acciones de Copilot

### Tarea 3.1: Realización de una solicitud de reserva

1. Selecciona el botón **Probar** en la parte superior derecha de la pantalla para abrir el panel de pruebas.

1. Selecciona los **tres puntos** en la parte superior del panel de pruebas en la parte superior derecha de la pantalla.

    ![Captura de pantalla de las opciones del panel Pruebas.](../media/test-pane-options.png)

1. Si no está habilitado, habilita **Realizar seguimiento de un tema a otro**.

1. Selecciona el icono **Iniciar una nueva conversación** en la parte superior del panel de pruebas.

1. Cuando aparezca el mensaje **Inicio de conversación**, el Copilot iniciará una conversación. Como respuesta, introduzca una frase desencadenadora para el tema que ha creado:

    `I want to book a real estate showing`

1. Escriba la siguiente información:

    ```
    Name: <Your name>
    Email address: <Your email address>
    ```

1. Después de proporcionar la información, una tarjeta adaptable muestra la información que has escrito y pregunta si los detalles son correctos. Seleccione **Sí**.

1. Selecciona **Casa** para el tipo de solicitud de propiedad.

1. Escribe `3` para el número de solicitudes de dormitorios.

    ![Captura de pantalla del panel de prueba con la información introducida.](../media/test-pane-action-results.png)

1. Escribe `Tomorrow 2:00 PM` en la indicación **¿En qué fecha y hora desea ver la propiedad?**.

1. Selecciona **Sí** en la indicación **¿Ha respondido a la pregunta?**.

1. Selecciona cualquier clasificación.

1. Selecciona **No** en el mensaje **¿Puedo ayudar con cualquier otra cosa?**.

### Tarea 3.2: Comprobación de la solicitud de reserva

1. Si aún no está abierta, ve a `https://make.powerapps.com` en una nueva pestaña.

1. Asegúrate de que estás en el entorno adecuado.

1. Selecciona **Reproducir** en la aplicación basada en modelo **Administración de propiedades inmobiliarias**.

1. En la navegación de la izquierda, selecciona **Solicitudes de reserva**.

    ![Captura de pantalla del portal Creador en la que se muestran los datos de la solicitud de reserva.](../media/booking-request-row.png)
