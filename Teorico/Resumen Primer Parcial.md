# Lo que entra 100% (si no me mintió notebook)
# Cohesión 
## Orientado a Funciones
1. Qué es?
	* La cohesión es un criterio INTRA-MODULAR, o sea que ocurre dentro de un módulo; representa cuán relacionados están los elementos de un módulo entre si.
2. Que buscamos?
	* Se busca una Alta Cohesión.
3. Niveles de Cohesión
	1. Casual.
		* Es la más débil de todas.
		* La relación entre los elementos de un módulo **no tienen significado**.
	2. Lógica.
		* Existe alguna relación lógica entre los elementos del módulo.
		* Los elementos realizan funciones dentro de la misma **clase lógica**.
	3. Temporal.
		* Parecido a cohesión lógica pero los elementos están **relacionados en el tiempo y se ejecutan juntos**.
	4. Procedural.
		* Contiene elementos que pertenecen a una misma **unidad procedural**.
	5. Comunicacional.
		* Tiene elementos que están **relacionados por una referencia al mismo dato**, o sea los elementos están juntos ya que **operan el mismo dato**.
	6. Secuencial.
		* Los elementos están juntos porque la **salida de uno corresponde a la entrada del otro**.
		* Puede contener varias funciones o parte de una.
		* Es relativamente buena cohesión y relativamente fácil de mantener, pero **difícil de reusar**.
	7. Funcional.
		* Es la más fuerte de todas.
		* Todos los elementos del módulo están **relacionados para llevar a cabo una sola función**.
![](recorte_20260902_221344.png)
## En el diseño Orientado a Objetos
A diferencia de la cohesión orientado a funciones, en el diseño de clases, existe 3 tipos de cohesión
1. **Cohesión de métodos**.
	* Se enfoca en por qué las lineas de código están juntas dentro de un método.
	* Es mayor si cada método implementa una única función claramente definida con todos sus elementos contribuyendo a implementar esta función.
	* Debe expresarse fácilmente con una oración simple.
2. **Cohesión de clases**.
	* Analiza por qué diferentes atributos y métodos residen bajo la misma clase.
	* Una clase debe representar y encapsular un único concepto. Si se encapsula múltiples conceptos, entonces se pierde cohesión.
		* Un síntoma de múltiples conceptos se produce cuando los métodos se pueden separar en diversos grupos, cada grupo accediendo a distintos subconjuntos de atributos.
3. **Cohesión de la herencia**.
	* Evalúa la justificación de por qué las clases están organizadas en una jerarquía.
	* La cohesión es más alta si la jerarquía se produce como consecuencia de la generalización-especialización.
# Acoplamiento
### ¿Qué es?
El acoplamiento es un concepto **inter-modular**, mide la fuerza de conexión o el nivel de interdependencia que existe entre los distintos módulos.
Captura la noción de dependencia. Cuanto más conocimiento técnico de un módulo `A` se requiera para poder comprender, modificar o solucionar un módulo `B`, mayor y más fuerte es la conexión (y por ende, el acoplamiento) entre ambos.
### ¿Qué se busca? Bajo Acoplamiento
El objetivo los módulos deben estar tan débilmente acoplados como sea posible. Cuando sea posible => módulos independientes.
### Factores que influyen en el acoplamiento
* **Tipo de conexiones entre módulos**
	* Bajo acoplamiento
		* Si la comunicación se realiza exclusivamente utilizando las entradas y salidas públicas y definidas en la interfaz del módulo.
	* Alto acoplamiento
		* Si se utilizan interfaces indirectas y oscuras, tales como acceder de forma directa a atributos u operaciones internas del módulo, o si se emplean variables compartidas (globales) entre distintos componentes.
* **Complejidad de las interfaces**
	* Bajo acoplamiento
		* Manteniendo las interfaces de los módulos tan simples y pequeñas como sea posible.
	* Alto acoplamiento
		* A medida que se incrementa la cantidad y complejidad de los parámetros pasados en la firma de una interfaz.
* **Tipo de flujo de información entre módulos**
	* Bajo acoplamiento
		* Los módulos se comunican pasando entradas de datos puros. Esto permite tratar al módulo receptor simplemente como una función matemática de entrada/salida que realiza transformaciones lógicas sobre los datos que recibe.
	* Alto acoplamiento
		* Se transfieren flags, banderas o señales de control. Esto significa que las acciones y la ejecución interna del módulo receptor dependerán directamente de esta información de control, lo que dificulta significativamente comprender y abstraer el módulo de forma aislada.
### Tipos de Acoplamiento en el Diseño Orientado a Objetos (OOD)
Debido a que en el paradigma orientado a objetos las clases y objetos encapsulan tanto estado como comportamiento, el acoplamiento se manifiesta en tres categorías específicas.
* **Acoplamiento por interacción**
	* Ocurre debido a que los métodos de una clase invocan a métodos de otra clase externa.
	* Cuando sube
		* Si los métodos acceden de forma directa a partes internas de otros métodos, 
		* los métodos manipulan directamente variables de otras clases, 
		* o si la información se pasa a través de variables temporales.
	* Cuando baja
		* si los métodos se comunican directamente a través de los parámetros: Con el menor número de parámetros posibles, pasando la menor cantidad de información posible, pasando sólo datos (y no control). 
* **Acoplamiento por componentes**
	* Ocurre cuando una clase `A` contiene o hace referencia a variables de otra clase `C`. Se presenta técnicamente en tres escenarios:
		* Si `A` tiene un atributo o variable de instancia de tipo `C`.
		* Si `A` define un método que recibe un parámetro de tipo `C`.
		* Si `A` define un método que utiliza variables locales de tipo `C` en su cuerpo de ejecución.
	* Cuando una clase `A` está acoplado con `C`, también está acoplado con todas sus subclases.
	* Cuando baja
		*  las variables de clase `C` en `A` son, o bien atributos, o bien parámetros en un método, o sea son visibles.
	* Cuando sube
		* Si la interacción se oculta dentro de variables locales internas de los métodos, lo que reduce la visibilidad de la dependencia externa ante otros desarrolladores.
* **Acoplamiento por herencia**
	* Dos clases están acopladas si una es subclase de otra.
	* Cuando sube
		* si las subclases modifican la signatura de un método o eliminan un método.
		* si, a pesar de mantener la signatura de un método se modifica el comportamiento de éste (debería preservar la pre/postcondición para que no sea malo).
	* Cuando baja
		*  la subclase sólo agrega variables de instancia y métodos pero no modifica los existentes en la superclase.
# Desafíos del Software
## Escala
* Los métodos de la IS deben tener la capacidad de adaptación y respuesta de un sistema con respecto al rendimiento del mismo, a medida que aumentan o disminuyen de forma significativa el número de usuarios o requerimientos del mismo.
## Productividad
* La IS está motivada por el costo y el cronograma, esto quiere decir que tanto una solución que demora mucho tiempo como una que entrega un software barato y de baja calidad son inaceptable.
* El costo del software es principalmente el costo de la mano de obra, por lo que se mide en Persona/Mes (PM).
* La Productividad (en términos de KLOC/PM) captura ambos conceptos. Si es más alta entonces menor costo y/o menor tiempo.
## Calidad
* Desarrollar software de alta calidad es un objetivo fundamental.
* La calidad se caracteriza a través de 6 atributos fundamentales
	* ### Funcionalidad
		* Capacidad de proveer funciones que cumplen las necesidades establecidas o implicadas.
	* ### Confiabilidad
		* Capacidad de realizar las funciones requeridas bajo las condiciones establecidas durante un tiempo específico.
	* ### Usabilidad
		* Capacidad de ser comprendido, aprendido y usado.
	* ### Eficiencia
		* Capacidad de proveer desempeño apropiado relativo a la cantidad de recursos usados.
	* ### Mantenibilidad
		* Capacidad de ser modificado con el propósito de corregir, mejorar o adaptar.
	* ### Portabilidad
		* Capacidad de ser adaptado a distintos entornos sin aplicar otras acciones que las provistas a este propósito en el producto.
* Confiabilidad es usualmente el principal criterio de calidad.
## Consistencia y Repetitividad
* Cómo asegurar que el éxito pueda repetirse, con el fin de mantener alguna consistencia en la calidad y la productividad.
* El objetivo de la IS es la sucesiva producción de sistemas de alta calidad y con alta productividad.
* La consistencia permite predecir el resultado del proyecto con certeza razonable. Sin consistencia sería difícil estimar costos.
## Cambio
* El software debe cambiar para adaptarse a los cambios de de empresas/instituciones.
* La práctica de la IS deben preparar el software para que éste sea fácilmente modificable. Los métodos que no permiten cambios, aún si producen alta calidad y productividad, son pocos útiles.
# Especificación de los Requerimientos
## Características de una SRS
### Correcta
* Cada requerimiento representa precisamente alguna característica deseada por el cliente en el sistema final.
### Completa
* Todas las características deseadas por el cliente están descriptas.
* Las características más difícil de lograr, para conseguirla uno debe detectar las ausencias en la especificación.
* Corrección y completitud están fuertemente relacionadas.
### No Ambigua
* Si para cada requerimiento existe un solo significado.
* La no ambigüedad es esencial para verificabilidad.
### Consistente
* Ningún requerimiento debe contradecir a otro.
### Verificable
* Si existe para cada requerimiento algún proceso efectivo que pueda asegurar que el software final satisface el requerimiento.
### Rastreable (Traceable)
* Se debe poder determinar el origen de cada requerimiento y cómo éste se relaciona a los elementos del software.
* Hacia adelante
	* Dado un requerimiento se debe poder detectar en qué elementos de diseño o código tiene impacto.
* Hacia atrás
	* Dado un elemento de diseño o código se debe poder rastrear que requerimientos está atendiendo.
### Modificable
* Si la estructura y estilo de la SRS es tal que permite incorporar cambios fácilmente preservando completitud y consistencia.
### Ordenada en aspectos de importancia y estabilidad
* Los requerimientos pueden ser críticos, importantes pero no críticos, deseables pero no importantes.
* Algunos requerimientos son esenciales y difícilmente cambien con el tiempo. Otros son propenso a cambiar.
* Entonces se necesita definir un orden de prioridades en la construcción para reducir riesgos debido a cambios de requerimientos.
# Punto Función (SRS)
* Es una métrica que estima el tamaño en términos de la funcionalidad.
* Requiere sólo de la SRS.
* Son 5 tipos de funciones que cada una tiene su función de complejidad Simple, Promedio, Compleja (pesos $w_{ij}$).
	* **Entradas externas**: Tipo de entrada (dato/control) externa a la aplicación.
	* **Salidas externas**: Tipo de salida que deja el sistema.
	* **Archivos lógicos internos**: Grupo lógico de dato/control de información generado/usado/manipulado.
	* **Archivos de interfaz externa**: Archivos pesados/compartidos entre aplicaciones.
	* **Transacciones externas**: I/O inmediatos (queries).
* $C_{ij}$ denota la cantidad de funciones tipo " $i$ " con complejidad " $j$ ".
* Punto función no ajustado (UFP): $$\sum^{5}_{i=1}\sum^{3}_{j=1}w_{ij}C{ij}$$
	* Ajustar el UFP de acuerdo a la complejidad del entorno.
	* Se evalúa según muchas características como por ejemplo:
		* Procesamiento distribuido.
		* Reusabilidad.
		* Objetivos de Desempeño.
		* Comunicación de Datos.
	* Cada uno de estos ítems debe evaluarse como:
		* No Presente (0).
		* Influencia Insignificante (1).
		* Influencia Moderada (2).
		* Influencia Promedio (3).
		* Influencia Significativa (4).
		* Influencia Fuerte (5).
	* Los valores de estos ítems es $p_i$.
* El Factor de Ajuste de Complejidad (CAF): $$0.65+0.01\sum^{14}_{i=1}p_i$$
* Punto Función = $CAF*UFP$.
# Arquitectura
### Qué es?
La Arquitectura del software de un sistema es la estructura del sistema que comprende los elementos del software, las **propiedades externamente visibles** de tales elementos, y la relación entre ellas.
## Vistas de la Arquitectura
### Módulo
* Un sistema es una colección de **unidades de códigos**, que no representan entidades en ejecución, o sea los elementos son módulos.
### Asignación de recursos
* Se enfoca en cómo las unidades de software se asignan a recursos como hardware, sistemas de archivos, etc.
	* O sea especifica la relación entre los elementos del software y las unidades de ejecución en el entorno.
* Exponen propiedades estructurales como qué proceso ejecuta en qué procesador, qué archivo reside dónde, etc.
### Componentes y Conectores
* Componentes: Son elementos computacionales o de almacenamiento de datos.
	* Cada componente tiene un nombre que representa su rol y le provee una identidad.
	* Cada componente tiene un tipo. Los distintos tipos se representan con distintos símbolos.
	* Las componentes utilizan interfaces o puertos para comunicarse con otras componentes.
![676](recorte_20260908_181251.png)
* Conectores: Son mecanismos de interacción entre los componentes.
	* Describen el medio en el cual la interacción entre componentes toma lugar.
	* Un conector puede proveerse por medio del entorno de ejecución.
	* Sin embargo, los conectores pueden también ser mecanismos de interacción más complejos.
	* No necesariamente son binarios.
	* Los conectores tienen: Nombre que identifican la naturaleza de la interacción y tipo, que identifica el tipo de interacción, binaria o n-aria, unidireccional o bidireccional, etc.
	* Muchas veces los conectores representan protocolos.
	* Los distintos tipos de conectores se representan con distintas notaciones.
![](recorte_20260908_181319.png)
Una vista C&C define las componentes y cómo se conectan entre ellas a través de conectores. Describe una estructura en ejecución del sistema; qué componentes existen y cómo interactúan entre ellos en tiempo de ejecución.
Es básicamente un grafo donde las componentes son los nodos y los conectores las aritas.
#### Estilos Arquitectónicos
Un estilo arquitectónico define una **familia de arquitecturas** que satisface las restricciones de ese estilo.
Los estilos proveen ideas para crear arquitecturas de sistemas.
##### Pipe and Filter
* Adecuado para sistemas que fundamentalmente realizan **transformaciones de datos**.
* Un sistema que usa este estilo utiliza una red de transformadores para realizar el resultado deseado.
* Tiene un sólo tipo de componente (Filtros) y un sólo de conector (Tubos).
* Un filtro realiza transformaciones y le pasa los datos a otro filtro a través de un tubo.
* Restricciones 1
	* Un filtro es una identidad **independiente** y asíncrona, o sea se limita a consumir y producir datos.
	* Un tubo es un canal **unidireccional** que transporta un flujo de datos de un filtro a otro.
	* Un tubo sólo conecta 2 componentes.
	* Los filtros deben hacer "**buffering**" y sincronización para asegurar el correcto funcionamiento como productor y consumidor.
* Restricciones 2
	* Cada filtro debe trabaja sin conocer la identidad de los filtros productores o consumidores.
	* Un tubo debe conectar un puerto de salida de un filtro a un puerto de entrada de otro filtro.
	* Un sistema **puro** de tubos y filtros usualmente requiere que cada filtro tenga su propio hilo de control.
##### Estilo de Datos Compartidos
* Tiene dos tipos de componentes; repositorios de datos y usuarios de datos.
	* El repositorio de datos provee almacenamiento permanente confiable.
	* Los usuarios de datos acceden a los datos en el repo, realizan cálculos y ponen los resultados otra vez en el repo.
	* La comunicación entre los usuarios sólo se hace a través del repo.
* En este estilo sólo hay un tipo de conector; lectura/escritura. 
* Tiene 2 variantes
	* Estilo Pizarra: Cuando se agregan/modifican datos en el repo, se infroma a todos los usuarios, o sea la fuente de datos compartidos es una entidad activa.
	* Estilo Repositorio: El repo es pasivo.
##### Estilo Cliente-Servidor
* Dos tipos de componentes; cliente y servidor
	* Los clientes sólo se comunican con el servidor, pero no con otros clientes.
	* La comunicación siempre es iniciada por el cliente quien le envía una solicitud al servidor y espera una respuesta de éste, entonces la **comunicación es usualmente asincrónica**.
* Solo un tipo de conector; solicitud/respuesta (request/reply), es asimétrico.
* Usualmente el cliente y el servidor residen en distintas máquinas.
## ATAM (Architecture Tradeoff Analysis Method)
Es una metodología que evalúa las consecuencias de las decisiones arquitectónicas en relación a diferentes atributos de calidad.
### Pasos Principales
#### 1. Recolectar Escenarios
*  Ponen a prueba una funcionalidad bajo condiciones específicas para evaluar si la arquitectura soporta los requisitos no funcionales.
	* Los escenarios describen las interacciones del sistema.
	* Elegir los escenarios de interés para el análisis.
	* Incluir escenarios excepcionales sólo si son importantes.
#### 2. Recolectar Requerimientos y/o Restricciones
* Define lo qué se espera del sistema en tales escenarios.
* Deben especificar los niveles deseados para los atributos de interés (preferiblemente cuantificados).
#### 3. Describir las Vistas Arquitectónicas
* Las vistas del sistema que serán evaluadas son recolectadas.
* Distintas vistas pueden ser necesarias para distintos análisis.
#### 4. Análisis Específicos a Cada Atributo
* Requisitos no funcionales pedidos por la calidad
	* Se analizan las vistas bajo distintos escenarios separadamente para cada atributo de interés distintos.
	* Esto determina los niveles que la arquitectura puede proveer en cada atributo.
	* Esto forma la base para la elección entre una arquitectura u otra o la modificación de la arquitectura propuesta.
	* Puede utilizarse cualquier técnica o modelado.
#### 5. Identificar Puntos Sensitivos y de Compromisos
* Análisis de sensibilidad
	* Cuál es el impacto que tiene un elemento sobre un atributo de calidad.
	* Los elementos de mayor impacto son los puntos de sensibilidad.
* Análisis de compromiso
	* Los puntos de compromiso son los elementos que son puntos de sensibilidad para varios atributos.
# Lo que entra un 70% (Si no me miente Kiara)
# Enfoque de la IS
* El proceso que se utiliza en la IS es el enfoque sistemático.
* El proceso de desarrollo consiste de varias fases,el motivo de separar en fases es la separación de incumbencias: Cada fase manipula distintos aspectos del desarrollo de software.
	* El proceso en fases permite verificar la calidad y progreso en momentos definidos del desarrollo (al final de la fase)
* Las fases son:
	* Análisis de requisitos y especificación.
	* Arquitectura.
	* Diseño.
	* Codificación.
	* Testing.
	* Entrega e instalación
# Análisis del Problema
El objetivo es lograr una buena comprensión de las necesidades, requerimientos y restricciones del software.

El principio básico que se utiliza es particionar el problema. Luego se comprende cada subproblema y la relación entre ellos con respecto a:
* Funciones: Análisis estructural.
* Objetos: Análisis OO.
* Eventos del Sistema: Particionado de eventos.
## Enfoque Informal
* No hay una metodología definida
* No se construye un modelo formal del sistema.
* La información recogida se plasma y organiza directamente en la SRS, la cual es el objetivo de revisión con el cliente.
* Depende de la experiencia del analista y el feedback del cliente en las revisiones.
## Modelado de Flujo de Datos
* Muy usado.
* Se enfoca en las funciones realizadas en el sistema, no en los requerimientos no-funcionales.
* Ve el sistema como una red de transformadores de datos sobre la cual fluye la información.
* Para el modelado utiliza el DFD y descomposición funcional.
La metodología de análisis y especificación estructurada utiliza DFD para organizar la información y guiar el análisis.
### DFD

### Método de Análisis Estructurado
* Muy usado para automatizar sistemas manuales ya existentes.
* Pasos Principales
	1. Dibujar el Diagrama de Contexto.
		* Ve el sistema completo como un transformador e identificar el contexto.
		* Es un DFD con un único transformador (El sistema), con entradas, salidas, fuentes y sumideros del sistema identificado.
	2. Dibujar el DFD del sistema existente.
		* El sistema actual se modela tal como es con un DFD con el fin de comprender el funcionamiento.
		* Se refina el diagrama de contexto.
		* Cada burbuja representa una transformación lógica de algunos datos.
		* Puede usar se DFD en niveles jerárquicos. Para obtenerlo se debe interactuar intensamente con el usuario.
		* El DFD obtenido se valida junto a los usuarios, haciendo una "caminada" a través del DFD.
	3. Dibujar el DFD del sistema propuesto e identificar la frontera hombre-máquina.
		* No existen reglas generales para dibujar el DFD del futuro sistema.
		* Se utiliza los conocimientos/comprensión existentes.
		* El DFD debe modelar el sistema propuesto completo: Ya sean procesos automatizados o manuales.
		* Se valida con el usuario, también esta parte.
		* Establecer luego la frontera hombre máquina: Qué procesos se automatizarán y cuáles permanecerán manuales.
		* Mostrar claramente la interacción entre los procesos manuales y los automáticos.




























# Yo en pandemia me la vi entera