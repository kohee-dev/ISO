# Sistemas operativos

Actualmente, un ordenador es una máquina muy compleja que puede constar de uno o más procesadores, discos, escáneres, tarjetas de comunicaciones, impresoras, módems, etc. Los dispositivos que contiene el ordenador son de tipo diverso (ópticos, magnéticos, etc.), tienen un funcionamiento muy variado, la tecnología de funcionamiento y el tipo de apoyo utilizado tienen características diferentes. Así, si un usuario quiere usar este sistema de manera eficiente, necesita conocer las características, controlar el funcionamiento, etc. Por lo tanto, hay que pensar que hay de haber una solución que permita a los usuarios utilizar esta máquina de una manera más sencilla, fácil y eficiente.

Podemos imaginar un sistema operativo como los programas que hacen utilizable el hardware. El hardware proporciona la “capacidad para operar” mientras que los sistemas operativos ponen esta capacidad de operación al alcance de los usuarios y administran de manera segura el hardware para conseguir un buen rendimiento.

Los sistemas operativos son los administradores de los recursos del sistema (procesadores, almacenamiento, dispositivos de E/S, datos, etc.).

En la imagen se muestran los niveles de software y hardware de un ordenador. También podéis observar como el sistema operativo es la única capa que trabaja directamente con el hardware. Por encima del sistema operativo se encuentra un nivel formado por los traductores, editores de texto y los intérpretes de órdenes. Esto nos permite crear varios niveles de abstracción que permiten trabajar con el ordenador de una forma mucho mas sencilla.

![alt text](../img/niveles.png)

La unión de los programas de las dos capas intermedias de la imagen conforman el software de sistemas de un ordenador. Finalmente, hay el nivel constituido por los programas de aplicación; estos programas no dan un servicio en otros programas, su finalidad es resolver problemas concretos. Son los programas que ejecuta un usuario no informático. Pertenecen a esta capa los procesadores de texto, las hojas de cálculo, las agendas electrónicas, los juegos, etc.

El hardware facilita los recursos básicos de computación, mientras que los programas de aplicación definen como se tienen que utilizar estos recursos para resolver los problemas de los usuarios. Puede haber molidos usuarios diferentes tratante de resolver problemas diferentes. Por consiguiente, es habitual la existencia de diferentes programas de aplicación. El sistema operativo controla y coordina el uso del hardware por parte de los diferentes programas de aplicación de los varios usuarios.

Los sistemas operativos construyen recursos de alto nivel que denominamos virtuales, a base de esconder los que realmente hay en el nivel bajo y que denominamos físicos. En consecuencia, desde el punto de vista del usuario o del proceso, la máquina física es convertida por el sistema operativo en una máquina virtual, también conocida como máquina extendida y que, a diferencia de la física, ofrece al usuario muchas más funciones y más comodidad en la hora de utilizarla.

Además, el sistema operativo proporciona servicios de los cuales no dispone el hardware, como por ejemplo la posibilidad de utilizar el ordenador por varios usuarios, la multiprogramación, etc.

## Tipos de sistemas operativos

- **Monolíticos:** Es la estructura de los primeros sistemas operativos, consistía en un solo programa desarrollado con rutinas entrelazadas que podían llamarse entre sí. Por lo general, eran sistemas operativos hechos a medida, pero difíciles de mantener.

![alt text](../img/monolitico.png)

- **Jerárquicos:** Conforme las necesidades de los usuarios aumentaron, los sistemas operativos fueron creciendo en complejidad y funciones. Esto llevó a que se hiciera necesaria una mayor organización del software del sistema operativo, dividiéndose en partes más pequeñas, diferenciadas por funciones y con una interfaz clara para interoperar con los demás elementos. Un ejemplo de este tipo de sistemas operativos fue MULTICS.

- **Capas**: El sistema operativo se organiza por capas, las capas superiores utilizan las inferiores. De esta forma, cada capa solo se fija en los detalles suyos. Un sistema de capas es THE

![alt text](../img/capas.png)

- **Microkernel**: los ordenadores son muy rápidos y se realizan muchos cálculos. Hay muchos fallos  (pocos para la cantidad de operaciones que realiza un PC). Para incrementar la tolerancia a fallos, se dividen en pequeños núcleos: operaciones de entrada/salida, gestión de memoria, del sistema de archivos, etc. Un sistema microkernel es MINIX

- **Cliente-servidor**: basándose en la estructura microkernel, se crea esta estructura, donde el cliente solicita una petición de un servicio en la red, y el servidor responde.

- **Máquina virtual**: integran distintos sistemas operativos en una sola máquina, dando la sensación de máquinas diferentes. En cada una de ellas, se puede ejecutar un sistema operativo distinto. Las máquinas virtuales las vamos a utilizar todo el curso, las más conocidas son VMware y VirtualBox. 


## Componentes de un sistema operativo

El núcleo es el módulo más bajo del sistema operativo, descansa directamente sobre el hardware del ordenador. Entre las tareas que hace hay la manipulación de las interrupciones, la asignación de trabajos al procesador y el de proporcionar un cauce de comunicación entre los diferentes programas.

En general, el núcleo se encarga de controlar el resto de los módulos y sincronizar la ejecución. El núcleo contiene:

- Un **planificador**, el cual se encarga de asignar el tiempo de procesador en los programas, de acuerdo con cierta política de planificación que varía de un sistema operativo a otro. Normalmente se utiliza una jerarquía de prioridades que determinan como se asignará el tiempo de CPU en cada programa. Una política de planificación muy común en los sistemas operativos multiprograma y multiacceso son las técnicas de time-slicing (fracción de tiempo). Se asigna en cada programa cierto intervalo de tiempo del procesador. Si el programa no ha acabado durante este tiempo, vuelve a la cola de programas.

- Submódulo para el control de **interrupciones** (*FLHI, first level interruption handler*). Este submódulo está vinculado al planificador, puesto que se utilizan interrupciones para modificar la seqüencialització del procesos. Es el encargado de dar respuesta a los cuatro tipos de interrupciones:
    - Interrupciones de programa
    - Interrupciones de reloj del sistema
    - Interrupciones de entrada/salida
    - Interrupciones por fallo del hardware
- **Comunicador de procesos** (semáforos, mecanismos de *waiting/signal*): encargado de evitar los bloqueos entre procesos, y ayuda a la volver a poner en marcha los procesos, tarea muy importante en el control de concurrencia en sistemas operativos multiprograma y de procesos distribuidos.

El núcleo del sistema operativo generalmente realiza las funciones siguientes:

- Manipulación de interrupciones.
- Creación y destrucción de procesos.
- Cambio de estados de procesos.
- Despacho (dispatcher).
- Suspensión y reanudación de procesos.
- Sincronización de procesos.
- Comunicación entre procesos.
- Manipulación de bloques de control de proceso.
- Apoyo de actividades de E/S.
- Apoyo de la asignación y desassignació de almacenamiento.
- Apoyo del sistema de archivos.
- Apoyo de mecanismos de llamamiento/retorno al procedimiento.
- Apoyo de ciertas funciones estadísticas del sistema.

El sistema operativo dispone de tres mecanismos de acceso al núcleo, pero el único de estos acontecimientos que puede usar el usuario para hacer una petición al sistema operativo es el salto no programado.

Un salto no programado se produce cuando el procesador ejecuta la instrucción de lenguaje máquina con saltos no programados. En la ejecución de esta orden están implicadas tres acciones: el cambio de modo de ejecución de modo usuario a modo núcleo, la ejecución de una rutina de servicio y el cambio de modo de ejecución de modo núcleo a modo usuario.