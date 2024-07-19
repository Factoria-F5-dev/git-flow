main# git-flow

<img src="https://www.zup.com.br/wp-content/uploads/2023/03/image1-2.png" style="width: 50%; height: auto;">

https://learngitbranching.js.org/?locale=es_ES

Es un modelo de ramificación que fue diseñado por un ingeniero de software llamado Vicent Driessen. Este modelo se publicó en el año 2010. En otras palabras, podemos decir que un ''git flow es una forma de trabajar o de cómo se debería trabajar de forma individual o grupal.''

# Ramas Principales: #

**Main(antes Master):**
Esta rama contiene el código estable y probado que se encuentra en producción. Las fusiones en esta rama generalmente se hacen desde la rama "release" después de un ciclo de lanzamiento exitoso. Se suelen nombrar con número de versión.

**Develop:**
Aquí es donde se integran todas las características completadas y se realizan pruebas de integración. Es una versión en desarrollo que aún no está lista para ser lanzada. Es desde donde se lanzan las características, features



# Ramas Temporales:

**Feature:**
Para implementar nuevas características o mejoras en el proyecto. Se crean a partir de la rama "develop". Una vez completada la función, se fusiona nuevamente con "develop".

**Release:**
Cuando se está preparando una nueva versión para su lanzamiento. Aquí se corrigen los errores menores y se realizan las pruebas finales. Se crea a partir de "develop" y se fusiona en ambas "master" y "develop" después de las pruebas exitosas.

**Hotfix:**
Para corregir problemas críticos en producción. Se crean a partir de "master", se corrige el error y se fusionan nuevamente en "master" y "develop" para asegurarse de que las correcciones también se reflejen en el desarrollo en curso.

Si utilizas Source Tree te da esta estructura por defecto:
<img src="https://jorgebenitezlopez.com/tiddlywiki/pro/sourtreeflow.png" style="width: 80%; height: auto;">

# Flujo de Trabajo:

* Inicia una nueva función creando una rama "feature" desde "develop".
* Trabaja en la función en la rama "feature" y realiza confirmaciones regulares.
* Una vez que la función está completa, fusiona la rama "feature" en "develop".
* Realiza pruebas y correcciones en la rama "release".
* Después de las pruebas exitosas, fusiona la rama "release" en "master/main" y "develop".
* Si surge un error en producción, crea una rama "hotfix" desde "master/main".
* Corrige el error en la rama "hotfix" y luego fusiona en "master" y "develop".

Git-flow proporciona un flujo estructurado que ayuda a los equipos a mantener un desarrollo organizado, versiones estables y la capacidad de trabajar en nuevas características y correcciones de errores de manera paralela. Sin embargo, también es importante adaptar el flujo según las necesidades específicas del proyecto y el equipo.

## Ventajas de Git Flow:
* Estructura clara que facilita la gestión de proyectos complejos.
* Separación del desarrollo de nuevas características, mantenimiento y lanzamientos.
* Flexibilidad para trabajar en múltiples características simultáneamente sin afectar la base de código principal.
* Facilita el despliegue y las actualizaciones de versiones de manera ordenada y predecible.

## Desventajas:
* Complejidad: Puede ser excesivo para proyectos pequeños o sencillos.
* Curva de aprendizaje: Requiere entender bien el modelo y seguirlo disciplinadamente.

Referencias: https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow

# Para crear ramas en git:

Para verificar ramas `git branch` y el status `git status`

Para crear una nueva rama en Git, puedes usar el comando git checkout -b <nombre_de_la_rama> Si deseas clonar la rama **main** y llamar a esta copia **dev**, primero debes asegurarte de estar en la rama main, y luego ejecutar el siguiente comando:

`git checkout -b dev`

Este comando creará una nueva rama llamada dev basada en la rama actual, que debería ser main si no has cambiado de rama. Después de ejecutar este comando, estarás en la nueva rama dev.

# Para fusionar o "mergear" ramas 

Para fusionar cambios de una rama (por ejemplo, la rama dev) con otra (la rama main), primero asegúrate de estar en la rama de destino (main). Puedes hacerlo utilizando el comando git checkout main. Luego, ejecuta el comando git merge seguido del nombre de la rama desde la cual deseas fusionar los cambios (dev en este caso).

1. Asegúrate de estar en la rama **main**:

`git checkout main`

2. Fusiona los cambios de la rama **dev** en la rama **main**:

`git merge dev`

Este comando fusionará los cambios de la rama dev en la rama main. Si hay conflictos durante la fusión, Git te pedirá que los resuelvas manualmente. Una vez que los conflictos se resuelvan (si los hay), los cambios de la rama dev estarán integrados en la rama main.

Cuando haya conflictos y no queramos aceptar el mergeo, ponemos este comando
`git merge --abort`

# Para subir una rama a github

1. Asegúrate de estar en la rama que deseas subir. Por ejemplo, si deseas subir la rama dev, puedes posicionarte primero en la rama en cuestión:
`git checkout dev`

2. Una vez que estés en la rama que deseas subir, utiliza el siguiente comando para subir la rama al repositorio remoto (en este caso, GitHub):
`git push -u origin dev`

Donde origin es el nombre del control remoto (el repositorio en GitHub) y dev es el nombre de la rama que deseas subir.

El uso de -u establece la rama remota como rama de seguimiento (tracking branch), lo que significa que en el futuro, puedes simplemente usar git push sin especificar la rama y Git sabrá a qué rama enviar los cambios.

Una vez ejecutado este comando, la nueva rama debería estar disponible en tu repositorio en GitHub. Puedes verificarlo visitando tu repositorio en la interfaz web de GitHub.

# Convenciones de nombres:

- Para nombrar ramas en GitHub cuando se trata de corregir errores en producción es utilizar el prefijo "hotfix-" seguido de una descripción breve y descriptiva del error o del cambio que se va a realizar. Ejemplo: hotfix-correccion-de-bug-123.
- De igual forma con "features", ejemplo: "feat-nueva-pagina-de-inicio".
- Ramas de lanzamiento (releases): Puedes usar un prefijo como "release-" o "v" seguido del número de versión y una breve descripción de los cambios que se incluyen en esa versión. Por ejemplo, "release-1.0.0" o "v2.1-beta".
- Tanto la rama "release", "feature" y "hotfix" una vez incorporadas a "dev" deberían de borrarse como buenas prácticas.
- Las ramas "release" y "feature" se crean desde "develop".
- La rama "hotfix" se crea desde "main", desde lo que está en producción.

  # Juego de Git

  https://learngitbranching.js.org/?locale=es_ES



