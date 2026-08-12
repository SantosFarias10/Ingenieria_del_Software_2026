# Dominio del Problema
>[!question] ¿Qué es el Software?
El Software es una colección de programas, procedimientos, y la documentación y datos asociados que determinan la operación de un sistema de computación
## Software de Nivel Industrial
### Diferencias entre el Software por Alumnos y de Nivel Industrial
La diferencia radica en:
* Calidad,
* Usabilidad,
* Confiabilidad,
* Portabilidad,
* etc.
## Demorado y Poco Confiable
Las fallas de software son distintas de las fallas mecánicas o eléctricas.
* En software, las fallas NO son consecuencias del uso y el deterioro.
* Las fallas ocurren como consecuencia de errores (o "bugs") introducidos **durante** el desarrollo.
* La falla que causa el problema existe desde el comienzo, sólo que se manifiesta tarde.
## Mantenimiento
### ¿Por qué es necesario el mantenimiento si el software no se deteriora con el uso?
* Para corregir errores residuales (**Updates**).
	* Mantenimientos correctivos.
* Para mejorar funcionalmente el software (**Upgrades**) y adaptarlos a los cambios de entorno.
	* Mantenimiento adaptativo.
# Desafíos de la Ingeniería del Software
>[!question] ¿Qué es la Ingeniería del Software?
>Aplicación de un enfoque sistemático, disciplinado, y cuantificable al desarrollo, operación, y mantenimiento del software.
* Enfoque sistemático: Metodología y prácticas existentes para solucionar un problema dentro de un dominio determinado. Esto permite repetir el proceso y da la posibilidad de predecirlo (independientemente del grupo de personas que lo lleva a cabo).
### Problema
El problema de producir software para satisfacer las necesidades del cliente/usuario guía el enfoque usado en IS (Ingeniería del Software).
Pero hay otros factores que tienen impacto en la elección del enfoque y son:
## Escala
Los métodos de Ingeniería del Software deben tener la capacidad de adaptación y respuesta de un sistema con respecto al rendimiento del mismo a medida que aumentan o disminuyen de forma significativa el número de usuarios o requerimientos del mismo.
## Productividad
Tanto una solución que demora mucho tiempo, como una que entrega un software barato y de baja calidad son inaceptables.
El costo del software es principalmente el costo de la mano de obra, por lo que se mide en Personas/Mes (PM).
* La productividad (en términos de `KLOC/PM`) captura ambos conceptos. Si es más alta => menor costo y/o menor tiempo.
## Calidad
* Desarrollar software de alta calidad es un objetivo fundamental.
* La calidad del software es difícil de definir (contrariamente al costo y al tiempo).
* El enfoque utilizado en la IS debe producir software de alta calidad.
Se define por los siguientes 6 puntos:
### Funcionalidad
Capacidad de proveer funciones que cumplen las necesidad establecidas o implicadas.
### Confiabilidad
Capacidad de realizar las funciones requeridas bajo las condiciones establecidas durante un tiempo específico.
### Usabilidad
Capacidad de ser comprendido, aprendido y usado.
### Eficiencia
Capacidad de proveer desempeño apropiado relativo a la cantidad de recursos usados.
### Mantenibilidad
Capacidad de ser modificados con el propósito de corregir, mejorar, o adaptar.
### Portabilidad
Capacidad de ser adaptado a distintos entornos sin aplicar otras acciones que las provistas a este propósito en el producto.
### En general
El concepto de calidad es específico al proyecto:
* En algunos casos la confiabilidad es más importantes, en otros la usabilidad.
* Para cada proyecto, el objetivo de calidad debe especificarse de antemano, y el objetivo del desarrollo será cumplir con el objetivo de calidad preestablecido.
En general la confiabilidad es usualmente el principal criterio de calidad.
#### Confiabilidad
La confiabilidad inversamente relacionada a la probabilidad de falla. Es difícil medir la cantidad de defectos.
* Más Fallas => Menos Confiable.
=> para normalizar:
* Calidad = densidad de defectos = Cantidad defectos en software entregado/tamaño.
## Consistencia y Repetitividad
### Desafío Clave en IS
Cómo asegurar que el éxito pueda repetirse, con el fin de mantener alguna consistencia en la calidad y la productividad.
### Objetivo de la IS
Es la **Sucesiva** producción de sistemas de alta calidad y con alta productividad.
#### Consistencia
La consistencia permite predecir el resultado del proyecto con certeza razonable. Sin consistencia sería difícil estimar costos.
## Cambio
* Cambio en las empresas/instituciones es lo habitual.
* El software debe cambiar para adaptarse a los cambios de dicha institución.
* Las prácticas de IS deben preparar al software para que éste sea fácilmente modificable. Los métodos que no permiten cambios, aún si producen alta calidad y productividad, son pocas útiles.
# Enfoque de la IS
Consistentemente desarrollar software de alta calidad y con alta productividad (**C&P**) para problemas de gran escala que se adapten a los cambios.
* C&P son los objetivos básicos a perseguir bajo gran escala y tolerancia a cambios.
* C&P son consecuencia de la gente, los procesos y la tecnología.
### Enfoque IS
La IS se enfoca mayormente en el proceso para conseguir los objetivos de calidad y productividad.
* El enfoque sistemático es realmente el proceso que se utiliza.
* La IS separa el proceso para desarrollar software del producto desarrollado (o sea, el software). Es aquí donde se distingue de las otras disciplinas informáticas.
* Premisa:
	* El proceso es quien determina, en buena medida, la C&P => un proceso adecuado permitirá obtener gran C&P.
* Diseñar el **proceso apropiado y su control** es el desafío clave de la IS.
## El Proceso Desarrollo en Fases
El proceso de desarrollo consiste de varias fases. Cada fase termina con una salida definida.
* Las fases se realizan en el orden especificado por el modelo de proceso que se elija seguir.
#### ¿Por qué se separa en fases?
El motivo de separar en fases es la **Separación de Incumbencias**
* Cada fase manipula distintos aspectos del desarrollo de software.
* El proceso en fases permite **Verificar la Calidad y Progreso** en momentos definidos del desarrollo, al final de la fase.
### Modelo de Procesos
Se han propuesto varios modelos de procesos para el desarrollo de software, y cada organización usa su propia variante.
En general consiste de:
1. Análisis y Especificación de Requerimiento.
2. Arquitectura.
3. Diseño.
4. Codificación.
5. ¡¡¡Testing!!!.
6. Entrega e Instalación.
Los enfoques sistemáticos requieren que cada etapa se realice rigurosa y formalmente.
## Administración del Proceso
La administración del proceso establece:
* Cómo asignar los recursos a las distintas tareas,
* Cómo organizarlas temporalmente,
* Cómo asegurar que cada fase de desarrolló apropiadamente,
* etc.
Sin la administración de procesos es virtualmente imposible cumplir con los objetivos de C&P.
