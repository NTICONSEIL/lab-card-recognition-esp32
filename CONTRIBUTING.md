# Règles de travail

## Branches et pull requests

- `main` est protégée : on n'y pousse jamais directement.
- Une branche par issue, nommée `<lot>/<numéro>-<sujet>`, par exemple `l3/12-matrice-confusion`.
- Une pull request par branche, liée à son issue (`Closes #12`), relue et approuvée par un membre d'**un autre lot** avant fusion.
- Fusion par *squash* pour garder un historique lisible.

## Messages de commit

Format court à l'impératif, préfixé par le lot :

```
L4: ajoute la capture JPEG à la demande
L2: corrige le découpage train/val/test
```

## Sécurité

- Aucun mot de passe, jeton, clé Wi-Fi ou certificat privé dans le dépôt.
- Les secrets du firmware vont dans `secrets.h` (ignoré par Git), à partir de `secrets.example.h`.
- Les secrets de la plateforme vont dans `platform/.env`, à partir de `platform/.env.example`.
- Un secret commité par erreur est considéré comme compromis : on le change, puis on prévient l'enseignant.

## Données

- Les images du jeu de données ne sont pas versionnées dans Git (trop volumineuses) ; elles sont stockées sur l'espace partagé du lab et référencées dans `dataset/README.md`.
- Le jeu de test est figé à la fin de la phase 2 : toute modification passe par une issue validée par l'enseignant.

## Revue hebdomadaire

Le chef de projet de la quinzaine (rôle tournant) ouvre chaque semaine une issue `Revue semaine N` à partir du modèle prévu, et y consigne l'avancement, les blocages et les décisions.
