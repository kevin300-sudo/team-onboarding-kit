# Dépannage Git et GitHub

Ce document recense les problèmes les plus fréquents rencontrés avec Git et GitHub, ainsi que les solutions à appliquer.

## 1. Je n'arrive pas à pousser mes modifications sur GitHub

Vérifiez d'abord que vous êtes sur la bonne branche :

```bash
git branch
```

Ensuite, poussez vos changements vers le dépôt distant :

```bash
git push origin <nom_de_votre_branche>
```

Si la commande échoue, vérifiez que :
- votre branche a bien été créée et sélectionnée ;
- vous êtes connecté à GitHub ;
- vous avez les droits d'écriture sur le dépôt.

## 2. J'ai une erreur de type "non-fast-forward"

Cela signifie que la branche distante a évolué et que votre branche locale est en retard.

Commencez par mettre à jour votre branche locale :

```bash
git fetch origin
git rebase origin/<nom_de_votre_branche>
```

Si le rebase crée des conflits, résolvez-les puis continuez :

```bash
git add <fichiers_resolus>
git rebase --continue
```

Lorsque le rebase est terminé, poussez à nouveau :

```bash
git push origin <nom_de_votre_branche>
```

## 3. J'ai un conflit lors d'un merge ou d'un rebase

Les conflits apparaissent lorsqu'une même ligne a été modifiée dans deux endroits différents.

Pour les résoudre :
1. ouvrez les fichiers en conflit ;
2. corrigez les sections marquées par Git ;
3. ajoutez les fichiers corrigés :

```bash
git add <fichier>
```

Puis continuez l'action :

```bash
git merge --continue
```

ou

```bash
git rebase --continue
```

## 4. Je ne vois pas mes fichiers modifiés dans Git

Vérifiez d'abord l'état du dépôt :

```bash
git status
```

Si les fichiers ne sont pas suivis, ajoutez-les :

```bash
git add <nom_du_fichier>
```

Ensuite, créez un commit :

```bash
git commit -m "Description claire des modifications"
```

## 5. Je veux récupérer les dernières modifications du dépôt distant

Pour mettre à jour votre branche locale avec les changements du dépôt distant :

```bash
git pull origin <nom_de_votre_branche>
```

Si vous travaillez sur une branche différente, vérifiez d'abord que vous êtes bien dessus :

```bash
git checkout <nom_de_votre_branche>
```

## 6. J'ai oublié de créer une branche avant de modifier le code

Créez une nouvelle branche à partir de la branche actuelle :

```bash
git checkout -b <nom_de_votre_branche>
```

Si vous avez déjà fait des modifications sur la branche principale, vous pouvez les sauvegarder avant de créer votre branche :

```bash
git stash
```

Ensuite, créez votre branche et réappliquez les changements :

```bash
git checkout -b <nom_de_votre_branche>
git stash pop
```

## 7. J'ai besoin d'annuler des modifications

Pour annuler les changements non validés dans un fichier :

```bash
git restore <nom_du_fichier>
```

Pour annuler un commit local :

```bash
git reset --soft HEAD~1
```

Pour supprimer complètement le dernier commit :

```bash
git reset --hard HEAD~1
```

Attention : `git reset --hard` efface définitivement les changements non poussés.

## 8. Je ne suis pas autorisé à pousser sur le dépôt

Cela peut venir de plusieurs causes :
- vous n'avez pas les droits d'écriture ;
- vous n'êtes pas authentifié auprès de GitHub ;
- le dépôt est protégé ou la branche est en lecture seule.

Vérifiez votre compte GitHub et vos permissions sur le dépôt, puis réessayez.

## 9. Je veux vérifier l'historique des commits

Pour afficher l'historique des modifications :

```bash
git log --oneline --decorate --graph --all
```

C'est utile pour comprendre où se trouvent les changements et identifier les commits à revoir.

## 10. Je veux supprimer une branche locale ou distante

Pour supprimer une branche locale :

```bash
git branch -d <nom_de_votre_branche>
```

Pour forcer la suppression :

```bash
git branch -D <nom_de_votre_branche>
```

Pour supprimer une branche distante :

```bash
git push origin --delete <nom_de_votre_branche>
```

## Conseils utiles

- Faites des commits réguliers et avec des messages clairs.
- Vérifiez toujours `git status` avant de commencer ou de finir une tâche.
- Gardez votre branche synchronisée avec la branche distante pour éviter les conflits.
- En cas de doute, utilisez `git status`, `git log` et `git fetch` pour diagnostiquer le problème.
