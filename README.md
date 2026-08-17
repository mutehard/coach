# Coach — hébergement

Ce dépôt ne sert qu'à **héberger** l'application, pour pouvoir l'ouvrir depuis l'iPhone
et l'ajouter à l'écran d'accueil. Ce n'est pas le dépôt de développement.

| Fichier | Rôle |
|---|---|
| `index.html` | L'application entière : un seul fichier HTML auto-contenu (CSS, JS et icônes embarqués). |
| `robots.txt` | Interdit l'indexation par les moteurs de recherche. |

## Source

Le fichier maître versionné vit hors de ce dépôt, dans le dossier de travail local du
projet, avec son `CONTEXTE.md` et ses versions archivées dans `Old/`.

## Mettre à jour

Depuis le dossier du projet :

```bash
python3 preparer-deploiement.py
cd Deploiement && git add -A && git commit -m "Coach vX.Y" && git push
```

Le script recopie la dernière version en `index.html`. GitHub Pages republie tout seul
en une minute environ.

## À ne pas faire

**Ne pas changer de compte GitHub.** L'origine au sens du navigateur est le domaine
`https://mutehard.github.io`, et le journal alimentaire est stocké par le navigateur de
l'iPhone sous cette origine. Renommer ce dépôt reste sans danger — le chemin change, pas
l'origine — mais publier depuis un autre compte afficherait une application vide.

Aucune donnée personnelle ni clé API ne se trouve dans ce dépôt : elles restent sur
l'iPhone. Une sauvegarde s'exporte depuis l'application, dans Réglages → Export JSON.

## `.nojekyll`

Ce fichier vide désactive le traitement Jekyll. Le site est un fichier HTML statique
unique : Jekyll n'y apporte rien et ajoute une étape de construction qui peut échouer —
ce qui est arrivé le 17 août 2026 sur la v9.0, avec un « Page build failed » sans détail.
Ne pas le supprimer.
