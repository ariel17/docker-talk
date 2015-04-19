========
 Docker
========

.. rst-class:: docker

   .. image:: _static/docker.png

.. rst-class:: movile

   .. image:: _static/movile.png

.. rst-class:: date

17 de Abril de 2015

.. rst-class:: me

   Ariel Gerardo Ríos

.. rst-class:: personal-data

   |email|

.. rst-class:: personal-data

   |twitter|_

.. _twitter: https://twitter.com/ariel_17_
.. |twitter| replace:: @ariel_17_
.. |email| replace:: ariel.rios@movile.com

Qué es Docker
=============

* Es una plataforma para desarrollar, desplegar y ejecutar aplicaciones
  distribuidas.

* Según `451 Research`_: *"Es una herramienta que puede empaquetar una
  aplicación y sus depedencias en un contenedor virtual que puede ejecutarse en
  cualquier servidor Linux."*

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

.. image:: _static/vm-stack.png

.. image:: _static/docker-stack.png

Por qué Docker
==============

* Hay una comunidad que comparte sus artefactos.

.. image:: _static/community.png

Cómo está compuesto
===================

Arquitectura
------------

* Motor: un contenedor de virtualización para el ambiente de las aplicaciones.
* Hub: un servicio para compartir y administrar las imágenes. 

Cómo está compuesto
===================

Imágenes
--------

Ejemplo de Dockerfile:

.. code-block:: text

   FROM ubuntu:14.10
   MAINTAINER Ariel Gerardo Ríos
   RUN apt-get install htop

   ADD . /code
   WORKDIR /code

   EXPOSE 80

   RUN echo "Hello world!"



Cómo se instala
===============

.. code:: bash

   ~$ sudo apt-get install docker

Cómo lo integro a mi desarrollo?
================================
