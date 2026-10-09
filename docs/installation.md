# Installation de l'environnement de travail

Cette procédure décrit les outils à installer pour rejoindre le travail de l'équipe. Elle s'adresse à un nouvel arrivant.

## Outils requis

- **Git** : le système de contrôle de version. Télécharger depuis git-scm.com.
- **VS Code** : l'éditeur de code. Télécharger depuis code.visualstudio.com.
- **Un compte GitHub** : avec la double authentification activée.

## Étapes

1. Installer Git, puis configurer son identité :

   ```bash
   git config --global user.name "Prenom Nom"
   git config --global user.email "prenom.nom@exemple.com"
   ```

2. Installer VS Code.

3. Cloner le dépôt de l'équipe :

   ```bash
   git clone https://github.com/VOTRE-COMPTE/team-onboarding-kit.git
   ```

4. Ouvrir le dossier du projet dans VS Code.

## Vérification

- `git --version` affiche une version.
- Le dépôt est cloné et s'ouvre dans l'éditeur.