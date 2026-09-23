# Laboratorio 1 - Entorno y puesta en marcha

En este laboratorio se cubrirá lo siguiente:
- Instalación del IDE VSCode y puesta en marcha de Git.
- Instalación del SGBD MariaDB Server.
- Instalación del cliente SQL HeidiSQL.
- Primeros pasos con HeidiSQL.
- Puesta en marcha del repositorio del proyecto de grupo.

## Instalación del IDE VSCode

En IISSI1 utilizaremos VSCode como IDE principal para las clases de laboratorio y para realizar las entregas del proyecto de curso usando Git.

Todos los repositorios remotos de Git estarán alojados en Github, con lo que, si no dispone de cuenta en GitHub, cree una en: https://github.com/. Recuerde registrarse con su correo electrónico de la Universidad de Sevilla.

Puede también explorar los beneficios como estudiante de la US para conseguir GitHub Pro aquí: https://github.com/education/students

Puede descargar VSCode en https://code.visualstudio.com/download. Cuando esté instalado, **necesita** clonar este repositorio para comprobar que todo funciona correctamente. 

Si no sabe cómo clonar un repositorio, puede seguir los pasos de la guía de introducción al uso de Git en VSCode: https://code.visualstudio.com/docs/sourcecontrol/intro-to-git. 

En esta asignatura haremos uso básico de Git: clonar repositorios, realizar conmmits, pushes, y, opcionalmente, pull requests y resolver los conflictos que puedan surgir entre componentes del grupo de proyecto. Si necesita refrescar los conceptos de Git, puede encontrar recursos online para entender los flujos básicos de trabajo. Por ejemplo: https://www.diegocmartin.com/tutorial-git/

## Instalación del SGBD MariaDB Server

MariaDB es un fork open-source de MySQL. Utilizaremos MariaDB como sistema gestor de base de datos (SGBD) en esta asignatura. Recuerde que el papel de este SGBD es escuchar instrucciones en SQL y realizar las funciones requeridas en dicha instrucción SQL (por ejemplo: creación de tablas, inserción/actualización de información, recuperar información, etc.).

Puede descargar MariaDB Server aquí: https://mariadb.org/download. Si necesita una guía paso a paso para entender qué está ocurriendo, haciendo especial énfasis en la **contraseña root, que deberá recordar (si quiere utilizar la misma configuración - recomendado - que en los ordenadores de laboratorio, establezca la contraseña iissi$root)** y la **instalación de MariaDB como servicio**, puede encontrarla aquí: https://www.mariadbtutorial.com/getting-started/install-mariadb/.

## Instalación del cliente SQL HeidiSQL

Una vez el servicio del SGBD MariaDB está corriendo, por defecto, MariaDB estará escuchando en el puerto 3306 de su ordenador, y puede utilizarlo a través de la línea de comandos. Si tiene curiosidad sobre cómo interactuar con MariaDB a través de terminal, puede encontrar ejemplos básicos aquí: https://www.mariadbtutorial.com/getting-started/connect-to-mariadb/

Debido a la dificultad que presenta para la mayoría de usuarios interacturar con un SGBD a través de líneas de comando, existen programas que facilitan la tarea de administración y gestión de BBDD. En esta sección instalaremos un software que nos permitirá comunicarnos con el SGBD visualmente, ayudándonos en las operaciones frecuentes en la administración de BBDD y ayuda en la escritura de SQL. 

En esta asignatura utilizaremos HeidiSQL. Puede descargarlo aquí: https://www.heidisql.com/download.php. Puede encontrar una ayuda aquí: https://www.heidisql.com/help.php.

## Primeros pasos con HeidiSQL

- Conecte con MariaDB Server utilizando el usuario root y la contraseña root especificado en la instalación de MariaDB Server. Si no se acuerda o la ha perdido, deberá desinstalar MariaDB Server y volver a instalarlo. Puede encontrar un paso a paso aquí: https://www.heidisql.com/help.php#connecting, pulse en +Nueva y deje los datos por defecto, solamente introduzca la contraseña de root especificada en la instalación.
- Cree una nueva base de datos llamada "nation" haciendo click derecho en la parte izquierda de la ventana de HeidiSQL, Crear nuevo -> base de datos. Nombre: nation, Collation: utf8mb3_general_ci.
- Cree un nuevo usuario llamado iissi_user. Para ello, clique en el botón de administrador de usuarios en la ventana de HeidiSQL (menú superior, 8º botón desde la izquierda con el icono de dos personas) -> Agregar -> Nombre de usuario: **iissi_user**. Contraseña: **iissi$user** (no le dé a Guardar aún).
- Asigne los permisos para administrar la BBDD recién creada: **nation** a **iissi_user** para así poder desconectarnos como root y tener menos privilegios, y, por ende, más seguridad. Para ello, haga clic en Agregar objeto y seleccione **nation** y haga clic en Aceptar. Tras esto, verá que hay un nuevo item en el menú de "Permitir acceso a:" llamado "Base de datos: nation". Marque el check para dar permiso a realizar todas las operaciones sobre la BBDD nation a iissi_user y pulse Guardar y posteriormente Cerrar.
- Ahora nos desconectaremos como root pulsando en el segundo icono por la izquierda del menú superior (el icono que represente a un enchufe desenchufado).
- En el administrador de sesiones, haremos clic en Nueva (abajo a la derecha), y renombraremos de Unnamed a iissi_user y cambiaremos el Usuario y la contraseña en el panel de la derecha. Usuario: iissi_user, Contraseña: iissi$user y pulse abrir. Ahora estamos conectados como iissi_user (no como root) y tenemos acceso a menos BBDD (hemos perdido acceso a aquellas BBDD de gestión de MariaDB), viendo la BBDD nation listada. Haga doble click sobre nation para seleccionar esa BBDD por defecto.
- Descargue el archivo nation.sql de este repositorio (o, alternativamente, descargue y descromprima el siguiente archivo: https://www.mariadbtutorial.com/wp-content/uploads/2019/10/nation.zip). Abra el archivo nation.sql con VSCode o con el editor de texto, y verá que dentro se encuentran numerosas instrucciones SQL, encargadas de crear una base de datos, una serie de tablas e introducir datos de prueba (puede ver de qué se trata aquí: https://www.mariadbtutorial.com/getting-started/mariadb-sample-database/). Para cargar este archivo en HeidiSQL (que enviará el SQL a MariaDB Server), pulse sobre Archivo -> Ejecutar Archivo SQL, selecciónelo y ejecútelo. Cuando termine, actualice (con la BBDD nation marcada, pulse sobre el 7º icono del menú superior, que es un icono de recarga en verde) y vea los cambios producidos. Explore HeidiSQL para familiarizarse con el entorno y explore la pestaña de Datos.
    

## Puesta en marcha del grupo

Para crear el repositorio del grupo, añadir a los compañeros como colaboradores y completar el formulario de registro, sigue las instrucciones de este documento:

👉 [Instrucciones para clonar el repositorio y configurar el grupo](https://github.com/IISSI1-IS-2026/plantilla-proyecto-curso/blob/main/INSTRUCCIONES_CLONAR_REPOSITORIO.md)

**IMPORTANTE**: Ante cualquier problema, ponte en contacto con tu profesor de laboratorio.

