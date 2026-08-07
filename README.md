# Foodvisor — hébergement

Ce dépôt ne sert qu'à **héberger** l'application, pour pouvoir l'ouvrir depuis l'iPhone
et l'ajouter à l'écran d'accueil. Ce n'est pas le dépôt de développement.

| Fichier | Rôle |
|---|---|
| `index.html` | L'application entière : un seul fichier HTML auto-contenu (CSS, JS et icônes embarqués). |
| `robots.txt` | Interdit l'indexation par les moteurs de recherche. |

## Source

Le fichier maître versionné vit hors de ce dépôt, dans
`Foodvisor vX.Y.html`, avec son `CONTEXTE.md`
et ses versions archivées dans `Old/`.

## Mettre à jour

```bash
python3 preparer-deploiement.py
cd Deploiement && git add -A && git commit -m "Foodvisor vX.Y" && git push
```

Le script recopie la dernière version en `index.html`. GitHub Pages republie tout seul
en une minute environ.

## À ne pas faire

**Ne pas renommer ce dépôt et ne pas changer de compte.** L'URL détermine l'origine au
sens du navigateur, et le journal alimentaire est stocké par le navigateur de l'iPhone
sous cette origine : une URL différente affiche une application vide. Le journal ne serait
pas perdu, mais deviendrait inaccessible.

Aucune donnée personnelle ni clé API ne se trouve dans ce dépôt : elles restent sur
l'iPhone. Une sauvegarde s'exporte depuis l'application, dans Réglages → Export JSON.
