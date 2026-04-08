# Site weco.coop

Site vitrine one-page de Weco (foncière solidaire). HTML/CSS/JS vanilla, zéro dépendance externe.

## Règles absolues

- Tout est dans `index.html` (HTML + CSS inline + JS inline)
- Images dans `assets/img/`, polices dans `assets/fonts/`
- Zéro dépendance externe : pas de CDN, pas de npm, pas de Google Fonts
- Commentaires en français
- Ne jamais casser le responsive (tester mentalement 375px, 960px, 1440px)
- Ne pas ajouter de features non demandées
- Garder le CSS dans le `<style>`, le JS dans le `<script>` (pas de fichiers séparés)

## Charte visuelle

Référence complète : `docs/charte-visuelle.md`

### Couleurs (variables CSS dans `:root`)

| Variable | Valeur | Usage |
|----------|--------|-------|
| `--bg-cream` | #f4f2ea | Fond principal |
| `--bg-yellow` | #ffff78 | Sections jaunes, surlignage |
| `--bg-purple` | #8b68c6 | Fond section équipe |
| `--accent-coral` | #e8755e | Titres h3, hover, accents |
| `--text-dark` | #303133 | Texte courant |
| `--text-purple` | #8b68c6 | Titres h1/h2, liens |
| `--text-white` | #ffffff | Texte sur fond violet |

Toujours utiliser les variables CSS (`var(--accent-coral)`), jamais les codes hex en dur.

### Polices

| Police | Variable/famille | Usage |
|--------|-----------------|-------|
| BureauGrotesque FiveThree | `'BureauGrotesque'` | Par défaut : titres, nav, texte courant. Poids unique : 500. |
| Grenette Pro | `'Grenette Pro'` | Corps de texte alternatif. Classe `.body-text` ou appliqué directement. |
| Girott | `'Girott'` | Décoratif uniquement (titre "WECO" section contact). Classe `.font-girott`. |

Pas de bold (la police n'a qu'un poids). Pas de souligné. Mise en évidence = couleur ou surlignage jaune.

### Hiérarchie typographique

| Element | Taille | Style |
|---------|--------|-------|
| h1 | 35px | uppercase, letter-spacing 0.05em |
| h2 | 29px | uppercase, letter-spacing 0.05em, couleur variable selon section |
| h3 | 24px | `color: var(--accent-coral)`, pas d'uppercase |
| h4 | 20px | uppercase |
| body/p | 15px | |
| .lead | 18px (13px mobile) | Texte d'accroche |
| nav a | 12px | uppercase, letter-spacing 0.05em |

### Surlignage

```html
<span class="highlight">texte surligné</span>
```
Fond jaune `var(--bg-yellow)`, utilisé dans les titres et accroches. Défini sur `.dispositif-intro .highlight` et `.innovation .lead .highlight`.

## Structure des sections

Le site a 11 sections dans cet ordre. Ne pas changer l'ordre sans validation.

| # | Section | Classe CSS | Fond | ID (ancre) |
|---|---------|-----------|------|------------|
| 1 | Hero | `.hero` | crème | - |
| 2 | Dispositif intro | `.dispositif-intro` | crème | `#le-dispositif` |
| 3 | Dispositif détails | `.dispositif-details` | jaune | - |
| 4 | Contexte | `.contexte` | crème | `#le-contexte` |
| 5 | Innovation | `.innovation` | crème | `#innovation` |
| 6 | Schéma pleine largeur | `.full-image` | crème | - |
| 7 | Budget + Prix ESSEC | `.budget-prix` | crème | - |
| 8 | Développement | `.developpement` | crème | `#developpement` |
| 9 | Quatorze + Weco Invest | `.quatorze-weco` | crème | - |
| 10 | Équipe | `.equipe` | violet | `#equipe` |
| 11 | Partenaires + Contact | `.partenaires` | crème | `#partenaires`, `#contact` |

### Patterns de grille

Les sections utilisent CSS Grid. Pattern standard :

```css
.section .grid {
  display: grid;
  grid-template-columns: 1fr 3fr;  /* ou 2fr 1fr, 1fr 1fr, repeat(3, 1fr) */
  gap: 32px;                       /* ou 36px, 48px, 60px selon la section */
  align-items: start;              /* ou center */
}
```

Au responsive (max-width: 960px), toutes les grilles passent en `grid-template-columns: 1fr`.

### Composant : membre d'équipe

```html
<div class="team-member">
  <div class="photo">
    <img loading="lazy" src="assets/img/Prenom.jpg" alt="Prénom Nom">
  </div>
  <h4>Prénom Nom</h4>
  <p>Description du rôle</p>
</div>
```

- Photo : carré, 80x80px affiché, `border-radius: 50%`, `object-fit: cover`
- Grille équipe : 6 colonnes desktop, 3 tablette, 1 mobile
- Texte description : Grenette Pro, 13px

### Composant : navigation

- Header fixe, shrink au scroll (140px → 70px desktop, 80px → 60px mobile)
- Menu hamburger sous 960px
- Liens ancres avec highlight de la section active (JS)
- Hover : `color: var(--accent-coral)`

### Composant : scroll-to-top

Bouton circulaire fixe en bas à droite, apparaît après 400px de scroll.

## Images

| Type | Format | Taille source | Notes |
|------|--------|--------------|-------|
| Photos équipe | JPG | ~258x258 | Affichées en 80x80 arrondies |
| Illustrations | PNG | variable | `loading="lazy"` sauf hero |
| Logo | SVG | - | Affiché dans le header et le hero |
| Schémas | PNG | pleine largeur | `max-width: 100%` automatique |

Pour ajouter une image :
1. La placer dans `assets/img/`
2. Nom en PascalCase ou kebab-case, sans espaces ni accents
3. Optimiser le poids (< 500 Ko idéalement)
4. Toujours mettre un `alt` descriptif en français
5. Ajouter `loading="lazy"` sauf pour les images above-the-fold (hero)

## JavaScript

Le JS gère 3 comportements :
1. **Scroll** : bouton retour en haut + header shrink + highlight nav active
2. **Menu mobile** : toggle hamburger, fermeture au clic lien ou extérieur
3. **Performance** : `requestAnimationFrame` + `passive: true` sur le scroll

Optimisé avec un seul listener scroll fusionné. Ne pas ajouter de listeners scroll séparés.

## Responsive

Trois breakpoints :

| Breakpoint | Cible | Changements clés |
|-----------|-------|-------------------|
| > 960px | Desktop | Grilles multi-colonnes, header 140px, logo 130px |
| ≤ 960px | Tablette | Grilles en 1 colonne, menu hamburger, équipe en 3 colonnes |
| ≤ 600px | Mobile | Équipe en 1 colonne |

Un breakpoint supplémentaire à 1499px réduit la taille du `.lead` de l'innovation (18px → 16px).

## Checklist avant de pousser une modification

1. Le site s'affiche correctement en desktop (1440px)
2. Le site s'affiche correctement en mobile (375px)
3. Les couleurs respectent la charte (variables CSS)
4. Les images ont un `alt` en français
5. Pas de dépendance externe ajoutée
6. Le menu de navigation fonctionne (desktop + mobile)
7. Les liens ancres pointent vers les bonnes sections

## Déploiement

- **Preview** : chaque push sur `main` met à jour https://weco-coop.github.io/site-weco/
- **Production** : déploiement manuel via GitHub Actions (onglet Actions > "Déployer sur weco.coop" > Run workflow)
- Ne jamais modifier directement sur le serveur
- Workflow : modifier → push → vérifier preview → déployer quand satisfait
