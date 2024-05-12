# dimailhog Docker Image MAILHOG
Par [pctronique](https://pctronique.fr/) <br />
Version 1.0.0

<details>
  <summary>Table des matières</summary>
  <ol>
    <li><a href="#Présentation">Présentation</a></li>
    <li><a href="#Import-Email">Import Email</a></ul>
    <li>
        <a href="#Version">Version</a>
        <ul>
            <li><a href="#Modifier-les-versions">Modifier les versions</a></li>
            <li><a href="#Dernière-version">Dernière version</a></li>
        </ul>
    </li>
    <li><a href="#Docker-hub">Docker hub</a></li>
  </ol>
</details>

## Présentation

Pour créer une image docker mailhog qui fonctionne comme le mailhog/mailhog de docker.
Cette image permet d'utiliser le stockage (storage) sur Windows, Linux et Mac.
Il permet l'import d'email par défaut.

La version :
<ul>
  <li>Mailhog:v1.0.0</li>
</ul>

> [!NOTE]
> Récupérer l'image du dossier « image ».

## Import Email

Pour importer les emails :

Créer un dossier « config/data » (par exemple) dans votre projet.

Dans un fichier « docker-compose.yml » :
```
volumes:
    - ./config/data:/docker-entrypoint-initdata.d:rw
```

Placer dans le dossier des fichiers "@mailhog.example".

## Version

### Modifier les versions

Dans un fichier « docker-compose.yml » :

```
args:
    - VALUE_MAILHOG_VERSION=v1.0.0
```

### Dernière version

Pour installer la dernière version à partir du fichier :

Dans un fichier « docker-compose.yml » :

```
args:
    - VALUE_MAILHOG_VERSION=latest
```

## Docker hub

Pour le transmettre sur docker hub, il serait préférable d'avoir une version fixe de l'image.

Remplacer :
```
# config install nodejs
FROM debian:bookworm-slim

ARG VALUE_MHOG_VERSION
ENV DEF_MHOG_VERSION=${VALUE_MHOG_VERSION:-"v1.0.1"}
```

Par :
```
# config install nodejs
FROM debian:bookworm-slim

ENV DEF_MHOG_VERSION=v1.0.1
```
