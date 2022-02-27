Docker
=====

.. _installation:

Téléchargement de docker
------------
Lien de téléchargement: 
`Docker <https://www.docker.com/get-started>`_

Téléchargement de Terminal
------------
Lien de téléchargement: 
`Terminal <https://www.microsoft.com/store/productId/9N0DX20HK701>`_

Mettre à jour le noyau Linux pour les Windows
------------
Lien de téléchargement: 
`wsl_update_x64 <https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi>`_

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

Créer un fichier docker-compose.yml qui contient :

.. code-block:: console

    version: "3.9"
   
    services:
    db:
        image: postgres
        volumes:
        - ./data/db:/var/lib/postgresql/data
        environment:
        - POSTGRES_NAME=postgres
        - POSTGRES_USER=postgres
        - POSTGRES_PASSWORD=postgres
    web:
        build: .
        command: python manage.py runserver 0.0.0.0:8000
        volumes:
        - .:/code
        ports:
        - "8000:8000"
        environment:
        - POSTGRES_NAME=postgres
        - POSTGRES_USER=postgres
        - POSTGRES_PASSWORD=postgres
        depends_on:
        - db

Créer le projet Django
------------

Exécuter la commande dans le Windows Terminal :

.. code-block:: console

    docker-compose run web django-admin startproject ESGI_Movies .

Changer les droits sur les fichiers avec la commande :

.. code-block:: console

    chown -R $USER:$USER .

Connection à la base de données
------------

Dans le fichier movies\ESGI_Movies\settings.py:

    au début du fichier ajouter :

    .. code-block:: console

        import os

    remplacer “DATABASES”

    .. code-block:: console

        DATABASES = {
            'default': {
                'ENGINE': 'django.db.backends.postgresql',
                'NAME': os.environ.get('POSTGRES_NAME'),
                'USER': os.environ.get('POSTGRES_USER'),
                'PASSWORD': os.environ.get('POSTGRES_PASSWORD'),
                'HOST': 'db',
                'PORT': 5432,
            }
        }


Lancer le docker
------------

Avec le bouton “start”, puis “Open in browser”
La page d’installation est normalement afficher dans le navigateur