# Alberka Apps

Petites applications internes d'Alberka Piscine, installables sur téléphone et tablette (PWA).
Hébergement : GitHub Pages. Données : Firebase (projet `alberka-apps`, Authentication + Firestore + Storage).

| Appli | Dossier | Lien |
|---|---|---|
| PV de réception & dossiers clients | `pv/` | https://alberka-piscine.github.io/alberka-apps/pv/ |

## Accès
Une personne doit :
1. figurer dans la collection Firestore `membres` (document = son e-mail en minuscules, champ `role` : `admin`, `poseur` ou `commercial`) ;
2. avoir un compte dans Firebase → Authentication (e-mail + mot de passe).

## Règles de sécurité
À copier dans la console Firebase :
- `firebase/firestore.rules` → Firestore → Règles
- `firebase/storage.rules` → Storage → Règles

## Export du dossier (.zip) et téléchargement direct des PDF
Nécessite d'autoriser le site à lire les fichiers (CORS). Dans la console Google Cloud, ouvrir Cloud Shell puis :

```
gcloud storage buckets update gs://alberka-apps.firebasestorage.app --cors-file=cors.json
```
(après avoir créé `cors.json` avec le contenu de `firebase/cors.json`).
