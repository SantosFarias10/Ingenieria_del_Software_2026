# Modelo de Diagrama 
## Objetos
Lo caracteriza la **Identidad**
## Clases
Las clases son como el molde para los objetos
### Estructura
* Tipo,
* Atributos,
* Metodos.
### Características
* Polimorfismo:
	* Permite que los objetos tengan diferentes comportamientos al mismo método
* Abstracción,
* Encapsulamiento,
* Herencia,
## Diagrama de Clases
### ¿Qué describe el diagrama de clases?
Relaciones entre objetos
### Relaciones entre Clases/Objetos
* Asociación: A esta relacionado a B, `A --- B`.
* Agregación: A contiene a B, `A ---♢(Blanco) B`.
* Composición: Es un caso particular de Agregación, A contiene a B, pero A no puede "vivir" sin B, `A ---♢ B`.
* Herencia: A es B, `A ---> B`.
### Cardinalidades
* Relación uno(1) a uno(1).
* Relación uno(1) a muchos(`*`).
* Relación muchos(`*`) a muchos(`*`).
## Principios de Diseño
* Única Responsabilidad
* No repetirse a uno mismo (*Don't Repeat Your Self* (DRY)).
* Bajo Acoplamiento
	* Las clases deben tener pocas dependencias entre sí, minimizando el impacto de los cambios en una parte del sistema sobre otras partes.
* Alta Cohesión
	* Los elementos relacionados deben estar juntos, mientras que los elementos no relacionados deben estar separados creando clases enfocadas y especializadas.
## Arquitectura
* Estructura de clases
* ORM
* Bases de datos relacional
---
# Teórico
* **Ingeniería del software** es la aplicación de un enfoque sistemático disciplinado, y cuantificable al desarrollo, operación, y mantenimiento del software.
* Testing
	* Siempre se toma jejejojojuju
* Para el jueves
	* Leer Cap 1 y 3
## Dominio del Problema
### ¿Que es el Software?
Colección de programas, procedimientos, y la documentación y datos asociados que determinan la operación de un sistema de computación.
### Software a Nivel Industrial
#### Diferencia entre el software por alumno y nivel industrial
La diferencia radica en:
* La calidad,
* Usabilidad,
* Confiabilidad,
* Portabilidad,
* ...
### Demorado y Poco Confiable
Los errores de software siempre estuvo, no es una falla por consecuencia del uso o deterioro.
La falla que causa el problema existe desde el principio, solo que se manifiesta tarde.
### Pregunta del Parcial
Los desafíos de la IS (Ingeniería del Software).#
#### No olvidarse que la escala pasan cosas
Va para arriba o para abajo, viste como es.
## Desafíos de la IS
### Escala
Los métodos de IS deben tener la capacidad de adaptación y respuesta de un
sistema con respecto al rendimiento del mismo a medida que **aumentan o
disminuyen** de forma significativa el número de usuarios o requerimientos del
mismo.
### Productividad
### Calidad
Se define por los siguientes 6 puntos:
#### Funcionalidad
#### Confiabilidad
#### Usabilidad
#### Eficiencia
#### Mantenibilidad
#### Portabilidad
### Consistencia y Repetitividad
### Cambios
## Enfoques de la IS
