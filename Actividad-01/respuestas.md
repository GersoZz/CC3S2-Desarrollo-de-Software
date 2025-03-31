# Parte 1: Introducción a DevOps

## 1. ¿Por qué surgió la necesidad de DevOps en el desarrollo de software?

DevOps surgió debido a la necesidad de mejorar la colaboración entre los equipos de desarrollo y operaciones. Tradicionalmente, estos equipos trabajaban por separado, esto ocasionaba que las actualizaciones tardaran mucho y era difícil adaptarse rápido a los cambios tecnológicos y a las necesidades del negocio. DevOps busca integrar ambos equipos mediante automatización, integración y entrega continua, reduciendo los tiempos de despliegue y mejorando la calidad del software.

## 2. Explica cómo la falta de comunicación y coordinación entre los equipos de desarrollo y operaciones en el pasado llevó a la creación de DevOps.

En el pasado, los equipos de desarrollo se enfocaban en escribir código y entregar nuevas funcionalidades, mientras que el equipo de operaciones priorizaba la estabilidad del sistema. Esta falta de alineación generaba conflictos, ya que los cambios de software podían afectar negativamente la infraestructura y causar inestabilidad en producción. La falta de comunicación también dificultaba la resolución de problemas y aumentaba los tiempos de entrega. DevOps surgió como una solución para eliminar estos silos, fomentando la colaboración, la automatización y la integración de procesos.

## 3. Describe cómo el principio de mejora continua impacta tanto en los aspectos técnicos como en los culturales de una organización.

- **Aspecto cultural**: La mejora continua rompe con el esquema tradicional de trabajo aislado y especializado promoviendo el trabajo colaborativo entre los equipos de producción, pruebas y operaciones. Cuando estos equipos trabajan colaborativamente con el propósito de mejorar continuamente el software, la cultura del desarrollo se vuelve a una de constante comunicación y colaboración.

- **Aspecto técnico**: La mejora continua implementa herramientas y técnicas que aceleran el proceso de despliegue e implementación. Sin estas, el despliegue e implementación del software tomaría un ciclo de desarrollo demasiado largo como para implementar mejoras a un ritmo aceptable.

## 4. ¿Qué significa que DevOps no se trata solo de herramientas, individuos o procesos?

Significa que DevOps representa una metodología de desarrollo completa que involucra todas las partes del proceso y, además, un trabajo colaborativo continuo entre todos los grupos participantes. Las herramientas y procesos son esenciales pero poco útiles si no se usan bajo la metodología completa de DevOps, la cual requiere que todos los miembros trabajen bajo una cultura colaborativa y con procesos de desarrollo e implementación continuos.

## 5. Según el texto, ¿como contribuyen los equipos autónomos y multifuncionales a una implementación exitosa de DevOps?

Este tipo de equipos pueden adaptarse con mayor facilidad a cada fase del desarrollo y trabajar de forma independiente a las exigencias de otros equipos especializados. En un contexto en donde se busca una implementación, desarrollo, comunicación y colaboración continuas, estos equipos pueden lidiar mejor con las exigencias de la metodología DevOps, ya que pueden asumir distintos roles a través de las distintas fases del desarrollo y enfrentar con errores o cambios de especificaciones con mayor flexibilidad.




---

# Parte 2: Infraestructura como código, configuración, seguridad y administración

## 1. *¿Qué significa "desplazar a la izquierda" en el contexto de DevSecOps y por qué es importante?*

"Desplazar a la izquierda" se refiere a la práctica de realizar pruebas en etapas de producción tempranas, literalmente moviéndolas "a la izquierda" de la línea de tiempo de desarrollo. En DevSecOps, esto facilita la identificación y enumeración de riesgos de seguridad en el software lo más temprano posible, lo cual permite que se solucione más rápido en comparación a una enumeración tardía.

## 2. *Explica cómo IaC mejora la consistencia y escalabilidad en la gestión de infraestructuras.*

 - La IaC mejora la consistencia de la gestión de infraestructuras ya que la configuración de la infraestructura es fácilmente reproducible mediante un archivo de configuración. Esto permite que los desarrolladores trabajen con la misma infraestructura y evita inconsistencias en el desarrollo.
 - Debido a que la infraestructura es manejada como código, esta puede ser modularizada. Esto quiere decir que se pueden agregar o prescindir de módulos mientras se requieran en el desarrollo. Del mismo modo, el versionamiento permite mejorar la infraestructura y, una vez se requieran menos recursos, regresar a una versión anterior.

## 3. *¿Cuál es la diferencia entre monitoreo y observabilidad? ¿Por qué es crucial la observabilidad en sistemas complejos?*

El monitoreo es una parte de la observabilidad. El primero se encarga de recolectar información referente a los sistemas involucrados en el software desarrollado, como el uso de memoria, almacenamiento, carga en el CPU, etc. La observabilidad abarca el monitoreo e involucra un análisis complejo del software en si y el entorno en el que se encuentra.

La observabilidad es esencial en sistemas complejos por ofrecer herramientas para que los desarrolladores comprendan el comportamiento de su software y de los recursos que usa o problemas que encuentra. En un contexto de varios componentes y módulos en un entorno complejo, lo cual ralentiza su proceso de desarrollo y puede llevar a mayores errores o confusiones por un pobre análisis.

## 4. *¿Cómo puede la experiencia del desarrollador impactar el éxito de DevOps en una organización?*

Un desarrollador experimentado permite identificar etapas a lo largo del desarrollo en las que no se siga la metodología DevOps. Además, un desarrollador experimentado con conocimientos de seguridad sigue buenas prácticas de desarrollo y pruebas y puede guiar al equipo a seguir estos principios para evitar errores acumulados más adelante. En general, la experiencia en el desarrollo impacta positivamente en el proceso de DevOps de una organización.

## 5. *Describe cómo InnerSource puede ayudar a reducir silos dentro de una organización.*

InnerSource es una metodología de trabajo en la que el software desarrollado se hace de código abierto dentro de una organización, lo cual permite que cualquier miembro de cualquier equipo puede leer y colaborar en el código. Este acercamiento reduce los silos porque permite que cualquier miembro, sea de desarrollo, implementación o pruebas, pueda escribir y realizar PRs en cualquier momento del desarrollo. Además, cualquiera puede leer y reutilizar código visible en toda la organización, lo cual reduce el "hoarding" de código por parte de algún grupo. Es decir, los grupos ya no trabajan de forma aislada sin conocer el código que escriben entre ellos, sino que todos pueden ver lo que se ha escrito y en qué pueden colaborar, lo que promueve la transparencia y la responsabilidad compartida en el software.

## 6. *¿Qué rol juega la ingeniería de plataformas en mejorar la eficiencia y la experiencia del desarrollador?*

Aunque las herramientas y técnicas utilizadas en DevOps y la metodología de CI/CD aceleren el proceso de desarrollo y resulten en productos de mejor calidad y seguridad, estos todavía necesitan ser configurados y adaptados a cada equipo de desarrollo, y los desarrolladores mismos puede que no tengan los conocimientos suficientes para esto o simplemente no puedan lidiar con el software mismo y con las herramientas necesarias para desarrollarlo a la vez. La ingeniería de plataformas lidia con esto, enfocándose en desarrollar, adaptar y configurar las herramientas y entornos necesarios para cada equipo de desarrollo según sus necesidades. Al desarrollar y adaptar estas herramientas al desarrollador, este puede trabajar más eficientemente sin tener que preocuparse por las posibilidades que estas herramientas o procesos ofrezcan.