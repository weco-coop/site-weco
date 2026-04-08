# Guide - Site weco.coop

## C'est quoi ?

Le site vitrine de Weco. Une seule page HTML avec des images et des polices. Pas de WordPress, pas de framework, pas de base de données.

## Comment ça marche

Le site vit à 3 endroits :

1. **GitHub** (github.com/weco-coop/site-weco) : le code source. C'est ici qu'on fait les modifications.
2. **GitHub Pages** (weco-coop.github.io/site-weco) : la preview. Chaque modification poussée sur GitHub est visible ici en quelques minutes. C'est notre bac à sable.
3. **weco.coop** : le site public. On y envoie les modifications uniquement quand on est satisfait de la preview.

En résumé : **on modifie sur GitHub, on vérifie la preview, on publie quand c'est bon.**

## Modifier le site avec Claude Code

### Pourquoi Claude Code ?

Claude Code est un assistant IA qui peut modifier le code du site à ta place. Tu décris ce que tu veux en français, il fait les changements. Pas besoin de savoir coder.

Le projet contient des fichiers de référence que Claude Code lit automatiquement :
- `CLAUDE.md` : les règles du site (couleurs, polices, contraintes)
- `docs/charte-visuelle.md` : la charte graphique complète

Claude Code respecte ces règles à chaque modification. Il ne va pas casser le style du site.

### Installation (une seule fois)

1. Créer un compte sur https://claude.ai si tu n'en as pas
2. Télécharger Claude Code Desktop : https://claude.ai/download
3. L'installer et se connecter avec ton compte Claude

### Ouvrir le projet

1. Ouvrir Claude Code Desktop
2. Aller dans File > Open Repo
3. Coller l'URL : `https://github.com/weco-coop/site-weco`
4. Claude Code clone le projet et charge automatiquement les règles du site

### Faire une modification

1. Décrire ce qu'on veut changer en français, par exemple :
   - "Change le numéro de téléphone par 06 12 34 56 78"
   - "Remplace la photo de Romain par celle-ci" (glisser la nouvelle photo dans la conversation)
   - "Ajoute un nouveau membre dans l'équipe : Marion, Directrice, avec cette photo"
   - "Change la couleur du fond en blanc"
   - "Mets à jour le texte de la section Dispositif avec ce nouveau texte : ..."
2. Claude fait la modification
3. Vérifier le résultat (Claude peut ouvrir une preview locale)
4. Si c'est bon, dire "pousse sur GitHub"
5. Attendre 2-3 minutes, vérifier sur la preview : https://weco-coop.github.io/site-weco/

### Ce qu'on peut modifier facilement

- Textes (titres, paragraphes, coordonnées)
- Photos (équipe, illustrations)
- Couleurs
- Ajout/suppression de membres d'équipe
- Liens et coordonnées

### Ce qui demande plus d'attention

- Changer la structure des sections (ordre, mise en page)
- Modifier les animations
- Ajouter de nouvelles sections entières

## Publier sur weco.coop

Quand la preview est bonne et qu'on veut mettre à jour le site public :

1. Aller sur github.com/weco-coop/site-weco
2. Cliquer sur l'onglet **Actions** (en haut)
3. Dans la liste à gauche, cliquer sur **Déployer sur weco.coop**
4. Cliquer sur le bouton **Run workflow** (bandeau bleu à droite)
5. Confirmer en cliquant sur le bouton vert **Run workflow**
6. Attendre que le job passe au vert (1-2 minutes)
7. Vérifier sur https://weco.coop

## Structure des fichiers

```
index.html              Le site (HTML + style + comportement, tout dedans)
assets/
  img/                  Les images (photos équipe, illustrations, logos)
  fonts/                Les polices de caractères
sitemap.xml             Pour le référencement Google
robots.txt              Pour le référencement Google
docs/
  charte-visuelle.md    Les couleurs, polices et règles graphiques du site
CLAUDE.md               Les règles que Claude Code suit automatiquement
GUIDE.md                Ce fichier
spec.md                 Les spécifications et historique du projet (état, décisions, phases)
.github/workflows/      Le script de déploiement automatique
```

## Charte visuelle (résumé)

| Element | Valeur |
|---------|--------|
| Fond | Crème #F4F2EA |
| Couleur principale | Corail #E8755E |
| Couleur secondaire | Violet #8B68C6 |
| Surlignage | Jaune #FFFF78 |
| Texte | #303133 |
| Police titres | BureauGrotesque |
| Police corps | Grenette Pro |
| Police décorative | Girott |

La charte complète est dans `docs/charte-visuelle.md`.

## Spécifications du projet (spec.md)

Le fichier `spec.md` contient la mémoire du projet : état actuel, décisions techniques, historique des phases et points à valider.

Quand on modifie le site (via Claude Code ou manuellement), `spec.md` doit être mis à jour avant de clôturer la session. Claude Code le fait automatiquement si on utilise le projet via Claude Code Desktop.

## En cas de problème

- **Le site public ne s'affiche plus** : vérifier la preview (GitHub Pages). Si elle marche, relancer le déploiement via Actions.
- **La preview est cassée** : aller sur GitHub, voir le dernier changement, et le reverser si besoin.
- **Claude Code ne se connecte pas au projet** : vérifier qu'on est bien membre de l'organisation weco-coop sur GitHub.
- **Besoin d'aide** : contacter Romain.
