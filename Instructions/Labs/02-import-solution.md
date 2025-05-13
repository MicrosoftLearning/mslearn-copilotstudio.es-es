---
lab:
  title: Importación de una solución de Dataverse
  module: Course Introduction
---

# Importación de una solución de Dataverse

En este ejercicio, importarás una solución de Dataverse que se usará para los siguientes laboratorios.

> **Nota**: en este ejercicio se supone que ya tienes una licencia de Copilot Studio o que te has registrado para obtener una [evaluación gratuita](https://go.microsoft.com/fwlink/p/?linkid=2252605) y tener un entorno de Power Apps en el que trabajar.

## Ejercicio 1: Importar una solución

En este ejercicio, importarás una solución de Dataverse en tu entorno que contiene las tablas necesarias para los laboratorios.

### Tarea 1.1: Inicio de sesión en Power Apps

1. En una pestaña nueva del explorador, ve a `https://make.powerapps.com`.

1. Si se te solicitan credenciales, inicia sesión con tu dirección de correo electrónico y la contraseña.

1. Si se te solicita información de contacto, establece el país o la región y selecciona **Introducción**.

1. En la parte superior derecha de la pantalla, comprueba que el **Entorno** está establecido en tu entorno. Aquí es donde trabajarás para la totalidad de los laboratorios. Si no es así, selecciona el entorno adecuado.

### Tarea 1.2: Descarga de la solución

1. Ve a [**Bookings_1_0_0_0.zip**](../../Allfiles/Bookings_1_0_0_0.zip) en GitHub. El archivo se encuentra en `https://github.com/MicrosoftLearning/mslearn-copilotstudio/blob/main/Allfiles/Bookings_1_0_0_0.zip`.

1. Selecciona los **puntos suspensivos (...)** cerca de la parte superior derecha y selecciona **Descargar**.

### Tarea 1.3: Importación de la solución

1. Ir a `https://make.powerapps.com`.

1. Asegúrate de que estás en el entorno adecuado.

1. En el panel de navegación izquierdo, seleccione **Soluciones**.

1. En la barra de herramientas situada en la parte superior, selecciona **Importar solución**.

1. Selecciona **Examinar**, busca el archivo **Bookings_1_0_0_0.zip** y selecciona **Abrir**.

    ![Solución para importar.](../media/solution-to-import.png)

1. Seleccione **Siguiente**.

1. Seleccione **importar**.

    La solución se importará en segundo plano. Esta operación puede tardar unos minutos.

    ![Solución importada.](../media/solution-imported.png)

    > **Alerta:** espera hasta que la solución haya terminado de importarse antes de continuar con el paso siguiente.

1. Cuando la solución se haya importado correctamente, abre la solución **Bookings**.

1. En el panel de navegación izquierdo, selecciona la pestaña **Información general**.

    ![Pestaña de información general de la solución.](../media/solution-overview.png)

1. Seleccione **Publicar todas las personalizaciones**.

### Tarea 1.4: Prueba de datos

1. En el panel de navegación izquierdo de la solución Bookings, selecciona la pestaña **Objetos**.

1. Selecciona los **puntos suspensivos (...)** en el menú para la aplicación basada en modelo de **administración de propiedades inmobiliarias** y selecciona **Reproducir**.

    ![Información general.](../media/play-app.png)

1. Seleccione **+ Nuevo**.

1. Introduzca los datos siguientes:

    - **Nombre de propiedad:**`1100 High Villas`
    - **Propietario:** selecciona tu usuario
    - **Precio de venta:**`250,000`
    - **Calle:**`Main Avenue`
    - **Ciudad:**`Redmond`
    - **Dormitorios:**`3`
    - **Baños:**`2`

    ![Información general.](../media/add-record.png)

1. Selecciona **Guardar y cerrar.**

1. Seleccione **+ Nuevo**.

1. Introduzca los datos siguientes:

    - **Nombre de propiedad:**`555 Oak Lane`
    - **Propietario:** selecciona tu usuario
    - **Precio de venta:**`300,000`
    - **Calle:**`Oak Lane`
    - **Ciudad:**`Denver`
    - **Dormitorios:**`4`
    - **Baños:**`3`

    ![Información general.](../media/add-record2.png)

1. Selecciona **Guardar y cerrar.**
