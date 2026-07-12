# Partee — Landing page "Bientôt disponible"

Ce dossier est **totalement indépendant** du code de l'app mobile Partee (React Native / Expo).
Il ne doit jamais être copié dans le repo de l'app — il vit dans son propre repo GitHub, dédié au site partee.be.

## Contenu

- `index.html` — la page complète (HTML + CSS inline, aucune dépendance externe sauf Google Fonts)
- `CNAME` — fichier requis par GitHub Pages pour attacher le domaine `partee.be`

## Ce qui a déjà été fait

- Design construit avec la palette officielle Partee (`constants/theme.ts` de l'app)
- Logo intégré (icône de l'app, encodée en base64 dans le HTML — aucun fichier image séparé à gérer)
- Fichiers prêts à être poussés tels quels sur GitHub (pas de dépendance, pas de build)

## Ce qu'il te reste à faire (accès à ton compte requis, je ne peux pas le faire à ta place)

### 1. Créer le repo sur GitHub

Va sur github.com → New repository → nomme-le par exemple `partee-landing` → **Public** → ne coche aucune option d'initialisation (pas de README, pas de licence) → Create repository.

### 2. Initialiser git et pousser ce dossier

Dans un terminal, sur ton Mac, à l'intérieur de ce dossier :

```bash
cd chemin/vers/partee-landing-final
git init
git add .
git commit -m "Landing page partee.be"
git branch -M main
git remote add origin https://github.com/TON-PSEUDO/partee-landing.git
git push -u origin main
```

(remplace `TON-PSEUDO` par ton nom d'utilisateur GitHub)

### 3. Activer GitHub Pages

Dans le repo GitHub → Settings → Pages → Source : branche `main`, dossier `/ (root)` → Save.
Dans le champ "Custom domain", entre `partee.be` → Save (GitHub va relire le fichier CNAME déjà présent).

### 4. Configurer le DNS chez Gandi

Dans l'espace Gandi → nom de domaine `partee.be` → DNS Records, remplace les enregistrements existants par :

| Type  | Nom | Valeur |
|-------|-----|--------|
| A     | @   | 185.199.108.153 |
| A     | @   | 185.199.109.153 |
| A     | @   | 185.199.110.153 |
| A     | @   | 185.199.111.153 |
| CNAME | www | TON-PSEUDO.github.io. |

### 5. Attendre et activer HTTPS

La propagation DNS prend de quelques minutes à quelques heures. Une fois que GitHub affiche un cadenas vert à côté du domaine dans Settings → Pages, coche "Enforce HTTPS".

## Vérification finale

Une fois en ligne, ouvre https://partee.be dans un navigateur privé (pour éviter le cache) et vérifie :
- la page s'affiche bien en HTTPS (cadenas)
- le lien mail en bas renvoie bien vers info@partee.be
- l'affichage est correct sur mobile (redimensionne la fenêtre ou teste depuis ton téléphone)
