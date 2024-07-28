# AutoDockerUpdate

Ce script Bash automatise le processus de mise à jour des conteneurs Docker en utilisant Docker Compose. Il vérifie les dernières images, recrée les conteneurs si des mises à jour sont disponibles et envoie des notifications à un canal Discord pour informer les utilisateurs de l'état de la mise à jour. Si aucun argument n'est fourni, le script liste les conteneurs disponibles et invite l'utilisateur à en sélectionner un pour la mise à jour.

## Table des matières
- [Prérequis](#prérequis)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Contributions](#contributions)
- [Licence](#licence)

## Prérequis
- Un système d'exploitation basé sur Linux (Debian recommandé).
- Docker et Docker Compose installés.
- Un webhook Discord pour envoyer des notifications.
- Un dossier unique contenant les différents dossiers des fichiers docker-compose.yml.

## Installation
1. Clonez ce dépôt :
   ```bash
   git clone https://github.com/Wolf117Warrior/AutoDockerUpdate.git
   cd AutoDockerUpdate
   ```
2. Rendez le script exécutable :
   ```bash
   chmod +x autodockerupdate.sh
   ```
3. Modifiez le script `update_docker.sh` pour ajouter votre webhook Discord et la modification du dossier contenant les fichiers Docker Compose :
   ```bash
   DISCORD_WEBHOOK="https://discordapp.com/api/webhooks/VOTRE_WEBHOOK_URL"
   CHEMIN="/votre/dossier/docker-apps/"
   ```

## Utilisation
Pour mettre à jour un conteneur Docker, exécutez le script en fournissant le nom du répertoire du conteneur :
```bash
./autodockerupdate.sh nom_du_répertoire_du_conteneur
```

Si vous exécutez le script sans argument, il listera les conteneurs disponibles et vous invitera à en choisir un pour la mise à jour.

## Exemple de notification
Des notifications sont envoyées à Discord pour indiquer :
- Le début de la vérification de mise à jour.
- Si une nouvelle version de l'image Docker est disponible ou si l'image est à jour.
- Le succès ou l'échec de la mise à jour du conteneur.
- Le nettoyage des images Docker inutilisées.
