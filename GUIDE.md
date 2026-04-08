# Guide - Site weco.coop

## C'est quoi ?

Le site vitrine de Weco. Une seule page HTML avec des images et des polices. Pas de WordPress, pas de framework, pas de base de données.

## Comment ça marche

Le site vit à 3 endroits :

1. **GitHub** (github.com/weco-coop/site-weco) : le code source. C'est ici qu'on fait les modifications. On peut les voir en preview avant de les publier.
2. **GitHub Pages** (weco-coop.github.io/site-weco) : la preview automatique. Chaque modification poussée sur GitHub est visible ici en quelques minutes.
3. **weco.coop** : le site public. On y envoie les modifications uniquement quand on est satisfait de la preview.

En résumé : **on modifie sur GitHub, on vérifie la preview, on publie quand c'est bon.**

## Modifier le site avec Claude Code

### Installation

1. Installer Claude Code Desktop (gratuit) : https://claude.ai/download
2. Se connecter avec son compte Claude
3. Ouvrir le repo GitHub : File > Open > coller l'URL `https://github.com/weco-coop/site-weco`

### Faire une modification

1. Ouvrir Claude Code Desktop
2. Décrire ce qu'on veut changer en français, par exemple :
   - "Change le numéro de téléphone par 06 12 34 56 78"
   - "Remplace la photo de Romain par celle-ci" (glisser la nouvelle photo)
   - "Ajoute un nouveau membre dans l'équipe : Marion, Directrice, avec cette photo"
   - "Change la couleur du fond en blanc"
3. Claude fait la modification et montre le résultat
4. Si c'est bon, dire "pousse sur GitHub"
5. Attendre 2-3 minutes, vérifier sur la preview : https://weco-coop.github.io/site-weco/

### Ce qu'on peut modifier facilement

- Textes (titres, paragraphes, coordonnées)
- Photos (équipe, illustrations)
- Couleurs
- Ajout/suppression de membres d'équipe
- Modification des liens

### Ce qui demande plus d'attention

- Changer la structure des sections (ordre, mise en page)
- Modifier les animations
- Ajouter de nouvelles sections

## Publier sur weco.coop

Quand la preview est bonne :

1. Aller sur github.com/weco-coop/site-weco
2. Cliquer sur l'onglet **Actions**
3. Dans la liste à gauche, cliquer sur **Déployer sur weco.coop**
4. Cliquer sur le bouton **Run workflow** (à droite)
5. Confirmer en cliquant sur le bouton vert **Run workflow**
6. Attendre que le job passe au vert (1-2 minutes)
7. Vérifier sur https://weco.coop

## Structure des fichiers

```
index.html          Le site (tout est dedans : HTML, CSS, JavaScript)
assets/
  img/              Les images (photos, illustrations, logos)
  fonts/            Les polices (BureauGrotesque, Grenette Pro, Girott)
sitemap.xml         Pour le référencement Google
robots.txt          Pour le référencement Google
.github/workflows/  Le script de déploiement automatique
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

## En cas de problème

- Le site public ne marche plus : vérifier sur la preview (GitHub Pages). Si la preview marche, relancer le déploiement depuis Actions.
- La preview ne marche plus : vérifier le dernier changement sur GitHub, annuler si besoin.
- Besoin d'aide : contacter Romain.
