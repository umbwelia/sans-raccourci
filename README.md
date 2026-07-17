# Sans Raccourci

Comprendre qui propose quoi, qui s'est vraiment engagé sur quoi ces dernières années, et comment les médias le racontent. Tous les bords au même niveau, chaque affirmation rattachée à sa source.

Ce n'est pas un site d'opinion. On rassemble des faits vérifiables, on les range de la même façon pour tout le monde, et le lecteur se fait son avis. Si la réponse tenait dans un titre, ce site n'existerait pas.

## Le principe

Le projet s'organise en trois couches.

**1. Les actes, pas les discours.** Ce sur quoi chaque personnalité a voté ou agi, au niveau de mandat qui est réellement le sien, à partir des données publiques.

**2. Les programmes.** Ce que chacun propose pour 2027, rangé dans la même grille thématique pour tous : économie, énergie et climat, institutions, social, immigration, Europe.

**3. Le cadrage médiatique.** Pour un même fait, comment différentes rédactions l'ont titré, avec la propriété du média affichée. On montre l'écart, on ne le commente pas.

La méthode et les règles de neutralité sont détaillées dans METHODE.md.

## Structure du dépôt

```
sans-raccourci/
├── index.html                       accueil, deux portes d'entrée
├── README.md                        vous êtes ici
├── METHODE.md                       règles de neutralité et de sourçage
├── assets/
│   └── styles.css                   style commun aux pages
├── data/
│   ├── candidats.json               source de vérité unique
│   ├── schema-candidat.json         forme d'un objet candidat
│   └── schema-vote.json             forme d'un vote isolé
├── themes/
│   └── theme.html                   vue de comparaison par thème (?t=cle)
├── candidats/
│   ├── candidat.html                vue d'un candidat (?c=slug)
│   └── _TEMPLATE.md                 gabarit de rédaction long format
├── comprendre/
│   └── les-niveaux-de-mandat.md     euro, ville, national : impact et intérêt
└── medias/
    └── qui-possede-quoi.md          comment on traite le cadrage médiatique
```

## Comment ça marche

Toute la donnée vit dans un seul fichier, `data/candidats.json`. Les trois pages (accueil, thème, candidat) le lisent. Ajouter un candidat ou une position à cet endroit le fait apparaître partout, sans double saisie. La vue par thème et la vue par candidat partagent donc exactement la même source.

Pour tester en local, les navigateurs bloquent la lecture de fichiers en `file://`. Lancer un petit serveur depuis le dossier suffit :

```
python3 -m http.server
```

puis ouvrir `http://localhost:8000`. Sur GitHub Pages, tout fonctionne directement.

## La règle de base

Chaque affirmation renvoie à sa source primaire. Une info sans source ne se publie pas.

Le projet vit sur GitHub pour cette raison : l'historique des commits rend chaque ajout et chaque correction traçable. Une erreur repérée se corrige par une issue ou une pull request, et la correction reste visible. C'est la meilleure garantie de sérieux.

## Non-partisan par construction

Aucun adjectif de valeur, aucun bord privilégié. Même grille, même profondeur, même ton pour tout le monde, de La France insoumise au Rassemblement national, de Renaissance aux Écologistes. Un déséquilibre repéré est un bug : signalez-le.
