# Site weco.coop

Site vitrine one-page de Weco (foncière solidaire). HTML/CSS/JS vanilla, pas de framework.

## Règles de modification

- Tout est dans `index.html` (HTML + CSS inline + JS inline)
- Images dans `assets/img/`, polices dans `assets/fonts/`
- Respecter la charte visuelle : voir `docs/charte-visuelle.md`
- Ne pas ajouter de dépendances externes (pas de CDN, pas de npm)
- Commentaires en français
- Garder le site responsive (mobile + desktop)

## Charte rapide

- Fond crème : #F4F2EA
- Corail (titres, accent) : #E8755E
- Violet (sections, liens) : #8B68C6
- Jaune (surlignage) : #FFFF78
- Texte : #303133
- Police titres : BureauGrotesque FiveThree
- Police corps : Grenette Pro
- Police décorative : Girott

## Déploiement

- Preview automatique : chaque push sur `main` met à jour https://weco-coop.github.io/site-weco/
- Production : déploiement manuel via GitHub Actions (onglet Actions > "Déployer sur weco.coop" > Run workflow)
- Ne jamais modifier directement sur le serveur

## Fichiers

```
index.html       Page unique du site
assets/img/      Images (PNG, JPG, SVG)
assets/fonts/    Polices (WOFF, WOFF2)
sitemap.xml      Référencement
robots.txt       Référencement
docs/            Documentation de référence
GUIDE.md         Guide de prise en main
```
