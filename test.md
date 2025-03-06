# 🛠 Git - Guide des Branches

## Introduction aux branches

### Concept de branche
```bash
git branch                         # Liste toutes les branches locales
```

Git permet de gérer les branches pour travailler sur plusieurs fonctionnalités ou correctifs en parallèle. Chaque branche est un environnement indépendant où les développeurs peuvent effectuer des modifications sans perturber le travail des autres. La branche principale est souvent appelée main ou master, mais des branches spécifiques peuvent être créées pour développer de nouvelles fonctionnalités, corriger des bugs ou expérimenter.

## Créer et basculer entre les branches

### Création d'une branche
```bash
git branch <nom_branche>           # Crée une nouvelle branche sans y basculer
```

Options disponibles :
```bash
git branch -v                      # Affiche la dernière validation sur chaque branche
git branch --merged                # Liste les branches déjà fusionnées dans la branche actuelle
git branch --no-merged             # Liste les branches non fusionnées dans la branche actuelle
```

### Basculer entre branches
```bash
git checkout <nom_branche>         # (Ancienne méthode) Change la branche actuelle
```

Options disponibles :
```bash
git checkout -b <nom_branche>      # Crée une nouvelle branche et y bascule immédiatement
git switch <nom_branche>           # (Nouvelle méthode depuis Git 2.23) Bascule vers une branche
git switch -c <nom_branche>        # (Nouvelle méthode) Crée une branche et y bascule
```

## Fusionner des branches

### Merge
```bash
git merge <branche_source>         # Fusionne la branche source dans la branche actuelle
```

Options disponibles :
```bash
git merge --no-ff <branche>        # Crée toujours un commit de fusion même si fast-forward est possible
git merge --abort                  # Annule une fusion en cours en cas de conflit
git merge --squash <branche>       # Combine tous les commits en un seul avant la fusion
```

### Rebase
```bash
git rebase <branche_source>        # Réapplique les commits de la branche actuelle sur la branche source
```

Options disponibles :
```bash
git rebase --continue              # Continue un rebase après résolution de conflits
git rebase --abort                 # Annule un rebase en cours
git rebase -i HEAD~<n>             # Rebase interactif pour les n derniers commits
```

## Gérer les conflits de merge

### Résolution de conflits
```bash
git status                         # Identifie les fichiers en conflit
```

Options disponibles :
```bash
git add <fichiers_conflits>        # Marque les conflits comme résolus après correction manuelle
git commit                         # Termine la fusion après résolution des conflits
git mergetool                      # Lance un outil graphique pour résoudre les conflits
```

## Envoyer des modifications vers un dépôt distant

### Push
```bash
git push origin <nom_branche>      # Envoie la branche locale vers le dépôt distant
```

Options disponibles :
```bash
git push --all origin              # Envoie toutes les branches locales vers le dépôt distant
git push --force                   # Force l'envoi même si l'historique distant diverge (avec précaution)
git push -u origin <branche>       # Pousse la branche et configure le suivi de la branche distante
```

## Récupérer les modifications d'un dépôt distant

### Pull
```bash
git pull                           # Récupère et fusionne les modifications du dépôt distant
```

Options disponibles :
```bash
git pull --rebase                  # Récupère les modifications et les applique avec rebase
git fetch                          # Récupère les modifications sans fusionner
git fetch --all                    # Récupère les modifications de tous les dépôts distants
```

## Travailler avec des forks et des pull requests

### Gestion des forks
```bash
git remote add upstream <url>      # Ajoute le dépôt original comme remote "upstream"
```

Options disponibles :
```bash
git fetch upstream                 # Récupère les modifications du dépôt original
git merge upstream/main            # Fusionne les modifications du dépôt original dans votre branche
git pull upstream main             # Récupère et fusionne les modifications du dépôt original
```

## 📝 Notes d'utilisation

### Format des commandes
- [ ] : paramètre obligatoire
- < > : paramètre optionnel
- | : choix entre plusieurs options

### Bonnes pratiques
- Créez des branches pour chaque nouvelle fonctionnalité ou correctif
- Utilisez des noms de branches descriptifs (feature/nom-fonctionnalité, bugfix/problème)
- Synchronisez régulièrement vos branches avec la branche principale
- Préférez le rebase pour garder un historique propre avant de fusionner dans main/master

### Points de vigilance
- Utilisez `git push --force` avec précaution car cela peut effacer le travail d'autres personnes
- Résolvez toujours complètement les conflits avant de terminer un merge/rebase
- N'utilisez pas rebase sur des branches partagées/publiées
- Vérifiez toujours que vous êtes sur la bonne branche avant de commencer à travailler
