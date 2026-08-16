# jhawla.github.io

Personal website — Jonathan Hawla, PhD student in cosmology, CEA Paris-Saclay.

Plain static HTML and CSS. No build step, no framework, no dependencies.
Editing a file and pushing is the whole workflow.

---

## Mise en ligne (une seule fois)

1. Sur GitHub, crée un dépôt **public** nommé exactement `jhawla.github.io`.
   Le nom doit correspondre à ton pseudo, sinon le site ne sera pas servi à la racine.
   Ne coche rien (pas de README, pas de .gitignore, pas de licence).

2. Dans un terminal, depuis ce dossier :

   ```bash
   git init
   git add .
   git commit -m "Site personnel"
   git branch -M main
   git remote add origin https://github.com/jhawla/jhawla.github.io.git
   git push -u origin main
   ```

3. Sur GitHub : `Settings` → `Pages` → sous *Build and deployment*,
   choisis **Deploy from a branch**, branche `main`, dossier `/ (root)`, puis `Save`.

4. Attends une à deux minutes. Le site est en ligne sur **https://jhawla.github.io**.

Pour toute mise à jour ensuite : modifie, puis `git add -A && git commit -m "..." && git push`.
Le site se redéploie tout seul en une minute environ.

---

## Fichiers à ajouter toi-même

Deux PDF sont référencés par le site mais absents du dossier `files/`.
Dépose-les avec **exactement** ces noms, sinon les liens renverront une 404 :

| Fichier attendu | Contenu |
|---|---|
| `files/Hawla_slides_GDR_CoPhy_2026.pdf` | Slides du GDR CoPhy, Clermont-Ferrand |
| `files/Hawla_poster_PheniicsFest_2026.pdf` | Poster du PheniicsFest |

Optionnel, si tu remets la main dessus : les slides d'Elbereth et du spotlight de Tucson.
Il faudra alors ajouter le lien à la main dans `index.html` (copie un bloc `<article class="entry">`).

**Remplace aussi `assets/photo.jpg`** par ton portrait en bonne résolution.
Celui qui s'y trouve a été récupéré depuis ton ancien CV et est de qualité insuffisante :
carré, au moins 600×600 px, visage centré.

---

## Mettre à jour le CV

Le CV est compilé depuis `cv_academique.tex` (hors de ce dépôt, garde-le dans Overleaf).
Ce fichier contient un interrupteur en haut :

```latex
\webversionfalse   % version complète : avec adresse postale et téléphone
\webversiontrue    % version publique : sans adresse ni téléphone
```

**Seule la version `\webversiontrue` doit être copiée dans `files/Hawla_CV.pdf`.**
La version complète est réservée aux candidatures envoyées par mail.
Ne publie jamais ton adresse personnelle et ton numéro sur une page indexée.

---

## Structure

```
index.html            la page entière
style.css             tous les styles
assets/field.jpg      fond : champ de matière généré par LPT
assets/photo.jpg      portrait
assets/favicon.svg    icône d'onglet
files/                CV, slides, poster
```

## Ajouter un talk

Dans `index.html`, section `#talks`, duplique un bloc et change les trois champs :

```html
<article class="entry">
  <div class="entry-date">Dec 2026</div>
  <div>
    <h3>Titre du talk<span class="tag">Talk</span></h3>
    <p class="entry-venue">Nom du meeting. Ville, pays.</p>
    <a class="pdf" href="files/nom_du_fichier.pdf">Slides (PDF)</a>
  </div>
</article>
```

Retire la ligne `<a class="pdf">` s'il n'y a pas de PDF associé.

## Nom de domaine personnalisé (facultatif)

Si tu achètes un domaine, ajoute un fichier `CNAME` à la racine contenant
uniquement le domaine, puis configure-le dans `Settings` → `Pages`.
