# Conventions de l'équipe

Ce document rassemble les conventions de travail de l'équipe. Il s'adresse à toute personne qui contribue au dépôt.

## Branches

- La branche `main` est toujours stable.
- Chaque modification se fait sur une branche dédiée, nommée par son intention : `ajout-...`, `correction-...`, `mise-a-jour-...`.

## Messages de commit

On suit la forme `type: description`, à l'impératif et en une ligne courte.

| Type    | Usage                                  |
|---------|----------------------------------------|
| docs    | documentation et contenus              |
| feat    | nouvelle fonctionnalité ou nouveau contenu |
| fix     | correction                             |
| chore   | organisation, configuration            |

Exemple : `docs: ajouter la procedure de sauvegarde`.

## Pull requests

- Toute contribution passe par une pull request vers `main`.
- La description explique ce que la pull request apporte.
- La branche est supprimée après la fusion.

## Mise en forme

Les documents sont rédigés en Markdown. Pour le code et les commandes, utiliser un bloc de code :

```bash
git status
```

## Checklist avant de proposer une contribution

- [ ] Le document est relu.
- [ ] Les liens fonctionnent.
- [ ] Le message de commit respecte la convention.

Pour toute question, ouvrir une [issue](https://github.com/VOTRE-COMPTE/team-onboarding-kit/issues).