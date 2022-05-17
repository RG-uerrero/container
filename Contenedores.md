# SISTEMAS DISTRIBUIDOS

## ALMANZA OROZCO EDUARDO ALMANZA
## ROBERTO CARLOS GUERRERO SILVA
## MEZA GAZABON JUAN PABLO
## RUIZ TORRES JAVIER DE JESÚS

---

## PRESENTADO A:
## RONALD ENRRIQUE CUELLO MEZA

---
## FUNDACIÓN UNIVERSITARIA TECNOLÓGICO COMFENALCO
## FACULTAD DE INGENIERIA
## INGENIERIA DE SISTEMAS
## SEMESTRE IX
## CARTAGENA DE INDIAS
## 2022

---

# CONTENEDORES

Es una funcionalidad a nivel de sistema operativo en la cual el kernel permite multiples instancias aisladas para un usuario, desde el punto de vista del programas o aplicaciones los contenedores lucen como si fueran computadoras completas.

Es un formato de empaquetado que agrupa todo el código y las dependencias de una aplicación en un formato estándar que le permite ejecutarse de manera rápida y confiable en todos los entornos informáticos.
CaaS son un servicio de nube que permite gestionar e implementar aplicaciones usando el aislamiento en contenedores, y que se puede implementar en las instalaciones o en la nube.

- Portabilidad: las aplicaciones desarrolladas en los contenedores tienen todo lo necesario para ejecutarse y pueden implementarse en varios entornos, los cuales incluyen las nubes privadas y las públicas. La portabilidad implica flexibilidad, ya que se pueden trasladar las cargas de trabajo entre los entornos y los proveedores con mayor facilidad.

- Escalabilidad: los contenedores se pueden ampliar a través de la incorporación de equipos, lo cual significa que un usuario puede multiplicar contenedores idénticos dentro de un mismo clúster para aumentar la capacidad cuando sea necesario. También se pueden reducir los costos considerablemente, ya que solo utiliza y ejecuta los sistemas que necesita, cuando los necesita.

- Eficiencia: los contenedores requieren menos recursos que las máquinas virtuales (VM), ya que no necesitan un sistema operativo aparte. Además, necesitan menos sistemas de hardware dedicado (bare metal) y se pueden ejecutar varios de ellos en un solo servidor, lo cual reduce los costos.
- Mayor seguridad: los contenedores se aíslan del resto, así que, si un contenedor se encuentra comprometido, los demás no se verán afectados.

- Velocidad: dado que no dependen del sistema operativo, se pueden iniciar y detener los contenedores en cuestión de segundos. Esta característica también permite aumentar la velocidad de las operaciones y el desarrollo, así como agilizar y simplificar la experiencia del usuario.

## ¿QUÉ ES DOCKER?

---
es una plataforma de software que permite crear, probar e implementar aplicaciones rápidamente, que facilitan la migración entre diferentes sistemas y garantiza el funcionamiento íntegro, evitando cualquier tipo de posible problema de dependencia entre versiones de software de los diferentes hosts. 
Esta empaqueta software en unidades estandarizadas llamadas contenedores que incluyen todo lo necesario para que el software se ejecute, incluidas bibliotecas, herramientas de sistema, código y tiempo de ejecución.

![Esta es una imagen](https://www.docker.com/wp-content/uploads/2022/03/horizontal-logo-monochromatic-white.png)

### ¿Como funciona?


Básicamente su funcionamiento se basa en compartir un único sistema operativo en la máquina que lo hospeda y en compartir bibliotecas entre contenedores.
Es un empaquetado de un programa o software, como pueden ser bases de datos, páginas web, programas phyton o cualquier otro tipo de software que optimiza el espacio ocupado y facilita la migración entre diferentes servidores.

### ¿CUÁNDO ES RECOMENDABLE USAR DOCKER?
Siempre que queramos simplificar el despliegue de aplicaciones, evitar conflictos entre programas y sistemas, o mejorar la consistencia entre entornos de desarrollo y de producción.


### VENTAJAS DE USAR DOCKER:
- Ahorro de costes de infraestructura
- Mayor productividad
- Mayor Compatibilidad
- Mayor seguridad
- Mayor seguridad por el aislamiento entre contenedores
- Autogestión de los contenedores
- Fiabilidad


## ¿QUÉ ES PODMAN?

---
es un motor de contenedores lanzado por primera vez en febrero de 2018 por la empresa de software estadounidense Red Hat, conocida principalmente por sus soluciones empresariales de alto rendimiento para diferentes proyectos de código abierto, como Red Hat Enterprise Linux (RHEL) u OpenStack. Basándose en la experiencia de Docker, en un principio estaba previsto que Podman no fuese un motor independiente, sino una herramienta de depuración sencilla para CRI-O, un plan que pronto se rechazó.
Este software de contenedores es similar a Docker en muchos aspectos y utiliza, por ejemplo, el mismo intérprete de línea de comandos que el estándar de la industria. Eso hace que sea incluso posible usar los típicos comandos de Docker en Podman. Para ello solo es necesario establecer el alias Docker=Podman. Así, cambiar de Docker a Podman suele ser relativamente sencillo. La innovación clave que Podman trae consigo es que renuncia a un daemon central como instancia de control para cada uno de los contenedores. Esto brinda la oportunidad de acceder a las distintas aplicaciones virtualizadas sin privilegios de root.

![Esta es una imagen](https://www.nicepng.com/png/full/539-5394306_intro-to-podman-podman-logo.png)


## ¿Como funciona?

- Es un motor de contenedores lanzado por primera vez en febrero de 2018 por la empresa de software estadounidense Red Hat, conocida principalmente por sus soluciones empresariales de alto rendimiento para diferentes proyectos de código abierto, como Red Hat Enterprise Linux (RHEL) u OpenStack. Basándose en la experiencia de Docker, en un principio estaba previsto que Podman no fuese un motor independiente, sino una herramienta de depuración sencilla para CRI-O, un plan que pronto se rechazó.

- Este software de contenedores es similar a Docker en muchos aspectos y utiliza, por ejemplo, el mismo intérprete de línea de comandos que el estándar de la industria.

- Otra de las características más destacadas de Podman son los denominados pods. Estos pods, inspirados en el concepto de los pods de Kubernetes, son la fusión de varios contenedores en un namespace común de Linux que comparten recursos concretos. De esta manera, se pueden combinar una amplia variedad de aplicaciones virtualizadas. A diferencia de Docker, Podman tiene soporte de primera clase para administrar múltiples contenedores. El modelo Pod simplifica el trabajo con varios servicios. Puede detener, reiniciar y eliminar todos los contenedores asociados mediante comandos de nivel de pod.

- Solo funciona en Linux, se debe correr en una máquina virtual con Linux, aunque puede ser conectado por SSH (acceso remoto a un servidor por medio de un canal seguro) a Windows o a Mac

### Instalación 

```
su -
subscription-manager repos --enable rhel-7-server-extras-beta-rpms
yum -y install podman

```

### Trabajar con contenedores e imágenes

```
podman pull my-image:latest

podman run my-image:latest --name my-container

podman ps

podman rm my-container

```

### Crear un pod
```
podman pod create --name my-pod
```

### Agregar un contenedor a un Pod
```
podman run --pod my-pod --name image-1 my-image:latest
podman run --pod my-pod --name image-2 another-image:latest
```

### Comandos de administracion:
```
podman kill my-pod      # Kill all containers
podman restart my-pod   # Restart all containers
podman stop my-pod      # Stop all containers
```