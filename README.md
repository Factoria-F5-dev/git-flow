# git-flow

Es un modelo de ramificación que fue diseñado por un ingeniero de software llamado Vicent Driessen. Este modelo se publicó en el año 2010. En otras palabras, podemos decir que un ''git flow es una forma de trabajar o de cómo se debería trabajar de forma individual o grupal.''

* Ramas Principales:

** Main(antes Master): Esta rama contiene el código estable y probado que se encuentra en producción. Las fusiones en esta rama generalmente se hacen desde la rama "release" después de un ciclo de lanzamiento exitoso. Se suelen nombrar con número de versión.

** Develop: Aquí es donde se integran todas las características completadas y se realizan pruebas de integración. Es una versión en desarrollo que aún no está lista para ser lanzada. Es desde donde se lanzan las características, features

* Ramas Temporales:

** Feature: Para implementar nuevas características o mejoras en el proyecto. Se crean a partir de la rama "develop". Una vez completada la función, se fusiona nuevamente con "develop".
** Release: Cuando se está preparando una nueva versión para su lanzamiento. Aquí se corrigen los errores menores y se realizan las pruebas finales. Se crea a partir de "develop" y se fusiona en ambas "master" y "develop" después de las pruebas exitosas.
** Hotfix: Para corregir problemas críticos en producción. Se crean a partir de "master", se corrige el error y se fusionan nuevamente en "master" y "develop" para asegurarse de que las correcciones también se reflejen en el desarrollo en curso.

* Flujo de Trabajo:

** Inicia una nueva función creando una rama "feature" desde "develop".
** Trabaja en la función en la rama "feature" y realiza confirmaciones regulares.
** Una vez que la función está completa, fusiona la rama "feature" en "develop".
** Realiza pruebas y correcciones en la rama "release".
** Después de las pruebas exitosas, fusiona la rama "release" en "master/maiin" y "develop".
** Si surge un error en producción, crea una rama "hotfix" desde "master/main".
** Corrige el error en la rama "hotfix" y luego fusiona en "master" y "develop".

Git-flow proporciona un flujo estructurado que ayuda a los equipos a mantener un desarrollo organizado, versiones estables y la capacidad de trabajar en nuevas características y correcciones de errores de manera paralela. Sin embargo, también es importante adaptar el flujo según las necesidades específicas del proyecto y el equipo.

Ventajas y desventajas

* Ventajas de Git Flow:
** Estructura clara que facilita la gestión de proyectos complejos.
** Separación del desarrollo de nuevas características, mantenimiento y lanzamientos.
** Flexibilidad para trabajar en múltiples características simultáneamente sin afectar la base de código principal.
** Facilita el despliegue y las actualizaciones de versiones de manera ordenada y predecible.

* Desventajas:
** Complejidad: Puede ser excesivo para proyectos pequeños o sencillos.
** Curva de aprendizaje: Requiere entender bien el modelo y seguirlo disciplinadamente.

Referencias: https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow
