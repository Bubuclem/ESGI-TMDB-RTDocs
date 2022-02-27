Docker
=====

.. _installation:

Téléchargement de docker
------------
Lien de téléchargement: `Get Started with Docker | Docker`_.
.. _Get Started with Docker | Docker: https://www.docker.com/get-started

`CNN <http://cnn.com>`_

Téléchargement de Terminal
------------
Lien de téléchargement: `Windows Terminal`_.
.. _Windows Terminal: https://www.microsoft.com/store/productId/9N0DX20HK701

Mettre à jour le noyau Linux pour les Windows
------------
Lien de téléchargement: `wsl_update_x64`_.
.. _wsl_update_x64: https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi

Une fois installer dans le Windows Terminal exécutez :

.. code-block:: console

   wsl --set-default-version 2

Installer une distribution Linux
------------

Créer un répertoire de travail sur votre machine avec Visual Studio
------------

Créer un fichier Dockerfile qui contient :

.. code-block:: console

    # syntax=docker/dockerfile:1
    FROM python:3
    ENV PYTHONDONTWRITEBYTECODE=1
    ENV PYTHONUNBUFFERED=1
    WORKDIR /code
    COPY requirements.txt /code/
    RUN pip install -r requirements.txt
    COPY . /code/

Créer un fichier requirements.txt qui contient :

.. code-block:: console
    
    Django>=3.0,<4.0
    psycopg2>=2.8

Créer le projet Django
------------

Connection à la base de données
------------

Lancer le docker
------------