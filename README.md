# dimailhog Docker Image MAILHOG
Par [pctronique](https://pctronique.fr/) <br />
Version 1.0.0

<details>
  <summary>Table des matières</summary>
  <ol>
    <li><a href="#Présentation">Présentation</a></li>
    <li>
        <a href="#Import-SGBD">Import SGBD</a>
        <ul>
            <li><a href="#Avec-docker-compose">Avec docker compose</a></li>
            <li><a href="#En-ligne-de-commande">En ligne de commande</a></li>
        </ul>
    </li>
    <li><a href="#Test-version">Test version</a></li>
    <li><a href="#Docker-hub">Docker hub</a></li>
  </ol>
</details>

## Présentation

Pour créer une image docker mailhog à partir du mailhog de docker.
Cette image permet d'utiliser le stockage (storage) sur Windows, Linux et Mac.
La version sur docker ne permet pas le stockage sur Linux, avec un problème de droit d'accès.

La version :
<ul>
  <li>Mailhog:v1.0.0</li>
</ul>

> [!NOTE]
> Récupérer l'image du dossier « image ».

## Docker hub

Pour le transmettre sur docker hub, il serait préférable d'avoir une version fixe de l'image.

Remplacer :
```
# variable environnement
ARG VALUE_MAILHOG_VERSION
ARG DEF_MAILHOG_VERSION=${VALUE_MAILHOG_VERSION:-"v1.0.0"}

# config install nodejs
FROM mailhog/mailhog:${DEF_MAILHOG_VERSION}
```

Par :
```
FROM mailhog/mailhog:v1.0.0
```
