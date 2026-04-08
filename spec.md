# Spec — Site Weco

## État
**Phase actuelle** : En ligne (déployé sur weco.coop, workflow GitHub → Gandi en place)
**Mode** : Express
**Dernière mise à jour** : 2026-04-08

## Brief
**Objectif** : Reproduire le site WordPress existant (quatorze.cc/weco) en site statique autonome, déployé sur weco.coop
**Public cible** : Collectivités, bailleurs sociaux, investisseurs solidaires, partenaires potentiels
**Pages prévues** : 1 page unique avec 11 sections (navigation par ancres)
**Fonctionnalités** : Navigation par ancres, responsive, pas de fonctionnalité complexe
**Identité visuelle** : Existante (voir brief pour détail couleurs, polices, logo)
**Contenu** : Repris du site actuel, certains textes à mettre à jour (équipe, contact)
**Contraintes** : Hébergement sur serveur propre Weco (weco.coop), assets autonomes (pas de dépendance quatorze.cc)

## Décisions techniques
**Stack** : HTML + CSS vanilla (polices et images hébergées localement)
**Hébergement** : Serveur Weco (weco.coop), pas Netlify
**Design system** : Reproduction fidèle du site existant
- Fond crème #F4F2EA
- Jaune #FFFF78 (sections dispositif-details)
- Corail #E8755E (primaire, titres)
- Violet #8B68C6 (accent, section équipe, liens)
- Texte #303133
- Polices : BureauGrotesque FiveThree (titres/nav), Girott (titre décoratif contact), Grenette Pro (corps de texte)

## Pages — état par page
| Page | Conception | Frontend | Contenu | Assets locaux | SEO | Status |
|------|-----------|----------|---------|---------------|-----|--------|
| index.html (11 sections) | ok | ok | ok | ok (17 img + 6 polices) | ok (meta, OG, favicon, sitemap, robots) | terminé |

## Audit de l'index.html (871 lignes)

### Ce qui est fait
- **Structure HTML** : 11 sections, bon ordre
- **CSS complet** (539 lignes) : variables couleurs, grilles, responsive (960px + 600px)
- **Navigation** : header fixe avec shrink au scroll, menu hamburger mobile, liens ancres, highlight section active
- **Scroll-to-top** : bouton flottant avec apparition progressive
- **Contenu texte** : complet et fidèle à l'original
- **Mise en page** : grilles 2/3 colonnes fidèles
- **Assets locaux** : 17 images + 6 polices dans `assets/`, zéro dépendance externe
- **SEO** : meta description, Open Graph (title, desc, image, url, locale), Twitter Card, favicon SVG, canonical, `lang="fr"`
- **sitemap.xml + robots.txt** : présents
- **HTML propre** : UTF-8 direct, pas d'entités HTML

## Points à valider avec Romain
1. **Équipe** : la composition a-t-elle changé depuis le site actuel ? (Margaux, Marion, Romain B. ?)
2. **Textes** : certains passages doivent-ils être mis à jour ? (objectifs 5 ans/10 ans, Montreuil)
3. **Contact** : l'adresse Halle aux Cuirs est-elle toujours correcte ? Numéro de téléphone ?
4. **Partenaires** : les logos partenaires sont-ils à jour ?
5. **Polices** : droits de licence pour héberger localement les fichiers WOFF2 ?
6. **Photos équipe** : les portraits actuels conviennent ou nouvelles photos ?
7. **Favicon** : en créer un à partir du logo ?

## Historique des étapes
### Phase 1 — Cadrage [TERMINÉ 2026-04-07]
- Site source scrapé (contenu markdown + branding + liens + structure)
- Site = 1 page WordPress avec 11 sections, navigation par ancres
- Seconde page (weeco-coop) : vide, pas à reproduire
- Assets identifiés : 12 images + 6 fichiers polices + 1 logo SVG
- Screenshots de référence conservés dans `screenshots/` (8 sections original + 9 sections local + 2 fullpage)
- Brief rédigé dans `.site-web-pipeline/brief.md`
- Mode Express détecté (1 page, pas de fonctionnalité complexe)

### Phase 2 — Conception [SAUTÉE - mode Express]

### Phase 3 — Développement [TERMINÉ 2026-04-08]
- Frontend : terminé (structure + CSS + JS + contenu + responsive)
- Assets : 17 images + 6 polices hébergées localement dans `assets/`
- SEO : meta description, OG, Twitter Card, favicon, canonical, sitemap.xml, robots.txt
- HTML nettoyé : UTF-8 direct, pas d'entités
- Review section par section avec Romain (2026-04-08) :
  - Innovation : titre violet (pas corail), lead surligné jaune, col-detail en BureauGrotesque, apports en violet + agrandi
  - Budget + Prix ESSEC : letter-spacing titre réduit, camembert agrandi + centré, colonnes centrées verticalement, texte bloc prix agrandi + BureauGrotesque explicite, image logos : grayscale + multiply pour fondre dans le jaune du bloc

### Phase 4 — Review [PARTIEL]
- Review visuelle faite sur sections Innovation et Budget/Prix ESSEC
- Sections restantes non encore relues en détail : dispositif, contexte, développement, quatorze/weco invest, équipe, partenaires/contact, footer

### Phase 5 — Mise en ligne [TERMINÉ 2026-04-08]
- **Hébergement** : Gandi Simple Hosting (PHP/MySQL), SFTP sur sftp.sd3.gpaas.net
- **Document root** : `/lamp0/web/vhosts/weco.coop/htdocs/`
- **Repo GitHub** : github.com/weco-coop/site-weco (public, org weco-coop)
- **Preview** : GitHub Pages → weco-coop.github.io/site-weco/
- **Déploiement** : GitHub Actions (workflow_dispatch = bouton manuel). Jamais automatique au push.
- **Workflow** : modifier localement ou via Claude Code → push sur GitHub → vérifier preview → cliquer "Deploy" dans Actions
- **Credentials SFTP** : stockés dans GitHub Secrets (SFTP_USER, SFTP_PASS), token jetable 30 jours
- **Guide collègue** : `GUIDE.md` dans le repo

## Notes et décisions en cours
- Le site WordPress original utilisait LayerSlider et Slider Revolution. Les dots de navigation latéraux étaient un artefact, non reproduits.
- L'adresse du site est passée de quatorze.cc/weco/ à weco.coop (domaine racine). Migration effective.
- HTML en UTF-8 direct (entités HTML nettoyées).
- Review visuelle en cours section par section avec Romain. Sections restantes à vérifier : dispositif, contexte, développement, quatorze/weco invest, équipe, partenaires/contact, footer.

## Repo GitHub
- **Repo** : github.com/weco-coop/site-weco (public, org weco-coop)
- **Fichiers repo** : index.html, assets/, sitemap.xml, robots.txt, CLAUDE.md, GUIDE.md, docs/charte-visuelle.md, .github/workflows/deploy.yml, spec.md
- **Preview** : weco-coop.github.io/site-weco/ (auto à chaque push)
- **Production** : weco.coop (déploiement manuel via GitHub Actions)
- **4 commits** à date (initial + deploy workflow + CLAUDE.md/guide + enrichissement CLAUDE.md)
