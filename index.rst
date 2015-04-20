========
 Docker
========

.. rst-class:: docker

   .. image:: _static/docker.png

.. rst-class:: movile

   .. image:: _static/movile.png

.. rst-class:: date

17 de Abril de 2015

Qué es Docker
=============

* Es una plataforma para desarrollar, desplegar y ejecutar aplicaciones
  distribuidas.

* Según `451 Research`_: *"Es una herramienta que puede empaquetar una
  aplicación y sus depedencias en un contenedor virtual que puede ejecutarse en
  cualquier servidor Linux."*


.. rst-class:: centered

   .. image:: _static/whatisdocker.jpg

.. _`451 Research`: https://451research.com/

Qué es Docker
=============

* Es un proyecto open source :)

.. image:: _static/github.png

Por qué Docker
==============

* Todos hablamos el mismo idioma.
* Disminuye la fricción de llevar aplicaciones a producción.
* Permite estandarizar diferentes ambientes (desarrollo, QA, producción) y
  clonarlos a demanda.

Por qué Docker
==============

* Menos recursos que una máquina virtual (mucho menos).


.. rst-class:: inline

   .. image:: _static/vm-stack.png

.. rst-class:: inline

   VS

.. rst-class:: inline

   .. image:: _static/docker-stack.png

Por qué Docker
==============

* Hay una comunidad que comparte sus artefactos.

.. image:: _static/community.png

Cómo está compuesto: Arquitectura
=================================

.. rst-class:: architecture

   .. image:: _static/architecture.svg

Cómo está compuesto: Arquitectura
=================================

* **Cliente:** es la interfaz de usuario para la administración de las imágenes
  y los contenedores.
* **Demonio:** es gestor de la plataforma de virtualización. Construye las
  imágenes, crea/destruye los contenedores, comunicación con el índice de
  imágenes, etc.
* **Imagen:** Es un template de sólo lectura
* **Contenedor:** es una instancia de una imágen (análogo a POO) ejecutándose.
* **Registros:** un servicio en línea para almacenar y compartir las
  imágenes; pueden ser públicos o privados.

Cómo está compuesto: Tecnología
===============================

.. rst-class:: interfaces

   .. image:: _static/interfaces.svg

Cómo está compuesto: Tecnología
===============================

* **Espacio de nombres:** *Namespaces*. Crea espacios de trabajo aislado entre
  contenedores.
* **Grupos de control:** *cgroups*. Limita, contabiliza y aisla el uso de
  recursos.
* **Formato del contenedor:** Formato de implementación del contenedor
  (libcontainer, LXC).

.. note:: 

   * Namespaces: cada aspecto del contenedor se ejecuta bajo su propio espacio
     de nombre y no tiene acceso a recursos por fuera de éste.
   
   * Cgroups: Por ejemplo, limitar la cantidad de memoria disponible para un
     contenedor.

Cómo está compuesto: Imágenes
=============================

Ejemplo de Dockerfile:

.. include:: examples/Dockerfile
   :literal:

Docker en acción
================

Creando una imagen:

.. code-block:: bash

   ~$ sudo docker build -t ariel17/image_name .
    Sending build context to Docker daemon 15.36 kB
    Sending build context to Docker daemon 
    Step 0 : FROM ubuntu:14.10
     ---> 59a878f244f6
    Step 1 : MAINTAINER Ariel Gerardo Ríos
     ---> Using cache
     ---> 9ccedeb1ff03
    Step 2 : RUN apt-get update
     ---> Using cache
     ---> 4cdb3613c092
    ...
    Step 8 : RUN echo "Hello world!"
     ---> Using cache
     ---> d8722569a228
    Successfully built d8722569a228

Docker en acción
================

Accediendo a una imagen por terminal:

.. code-block:: bash

   ~$ sudo docker run -ti --rm ariel17/image_name /bin/bash
   root@98bf7687450d:/code#

Ejecutando una imagen como demonio:

.. code-block:: bash

   ~$ sudo docker run -d -p 9999:80 ariel17/image_name
    a8f634e7882b8b1e7a8d9068018066f98d16ef8a55a303f0995b58e97ce6c768

¡Demo! :)
=========

.. note:: 

   * Build: sudo docker build -t ariel17/docker-talk .
   
   * Run tty: sudo docker run -ti --rm ariel17/docker-talk /bin/bash

   * Agregar ENTRYPOINT burnP6; htop + sudo docker run -ti --rm --cpuset=0 ariel17/docker-talk

   * Run background: sudo docker run -d -p 9999:80 --rm ariel17/docker-talk

   * Run 1 cpu: sudo docker run -d -p 9999:80 --rm ariel17/docker-talk

¿Preguntas?
===========

.. rst-class:: preguntas

   .. image:: _static/preguntas.gif

Dónde continuar
===============

* **Blog**: https://blog.docker.com/
* **Try it!:** https://www.docker.com/tryit/
* **Official documentation:** https://docs.docker.com/
* **Ansible & Docker:** http://www.ansible.com/docker
* **GitHub repository:** https://github.com/docker/docker
* **#Docker:** canal IRC de charlas en https://freenode.net/

¡Muchas gracias!
================

.. rst-class:: movile-thankyou

   .. image:: _static/movile.png

.. rst-class:: me

   Ariel Gerardo Ríos

.. rst-class:: personal-data

   |email|

.. rst-class:: personal-data

   |twitter|_

.. _twitter: https://twitter.com/ariel_17_
.. |twitter| replace:: @ariel_17_
.. |email| replace:: ariel.rios@movile.com
