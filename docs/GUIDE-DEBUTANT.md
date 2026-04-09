# Guide débutant — Modifier le site weco.coop

Bienvenue. Ce guide est fait pour toi si tu n'as jamais touché à GitHub ni à Claude Code, et que tu veux pouvoir modifier le site **weco.coop** sans rien casser. On va y aller pas à pas, sans jargon. Compte une heure pour tout installer la première fois. Ensuite, modifier le site te prendra quelques minutes.

Si tu bloques à une étape, ne force pas : note où tu en es et demande à Romain B. Il préfère mille fois t'aider que de réparer après coup.

---

## 1. Créer un compte GitHub

GitHub, c'est le coffre-fort où vit le code du site. Tout passe par là.

1. Va sur https://github.com
2. Clique sur **Sign up** (en haut à droite)
3. Utilise ton email Weco (`prenom@weco.coop`)
4. Choisis un nom d'utilisateur simple (par exemple `prenom-weco`)
5. Choisis un mot de passe solide et **note-le dans ton gestionnaire de mots de passe**
6. Valide l'email de confirmation que GitHub t'envoie

Voilà, tu as un compte. Tu n'as encore accès à rien, c'est normal.

## 2. Être invité dans l'organisation weco-coop

L'organisation `weco-coop` regroupe tous les projets de l'équipe. Tant que tu n'y es pas, tu ne vois pas le site.

1. Envoie ton **nom d'utilisateur GitHub** à Romain B. (par mail ou Slack)
2. Romain va t'envoyer une invitation depuis GitHub
3. Tu reçois un mail de GitHub avec le sujet *« You've been invited to join @weco-coop »*
4. Clique sur **View invitation** puis sur **Join @weco-coop**
5. Tu fais maintenant partie de l'organisation. Tu vois le projet `site-weco` dans ta liste.

## 3. Installer Claude Code Desktop

Claude Code, c'est l'outil qui va te permettre de **parler en français** à un assistant qui modifie le site pour toi. Pas besoin de coder.

1. Va sur https://claude.com/claude-code
2. Télécharge la version **Desktop** pour ton système (Mac ou Windows)
3. Lance l'installation, accepte les conditions
4. Au premier lancement, connecte-toi avec ton compte Anthropic (si tu n'en as pas, crée-le, c'est gratuit pour démarrer)

Tu as maintenant Claude Code Desktop ouvert. Pour l'instant il ne sait rien du site.

## 4. Connecter Claude Code à GitHub

C'est le pont entre les deux. Une seule fois à faire.

1. Dans Claude Code Desktop, ouvre les **paramètres** (icône engrenage)
2. Cherche la section **GitHub** ou **Integrations**
3. Clique sur **Connect GitHub**
4. Une page s'ouvre dans ton navigateur, GitHub te demande d'autoriser Claude Code
5. **Autorise l'accès à l'organisation `weco-coop`** (important, sans ça tu ne verras pas le site)
6. Reviens dans Claude Code, la connexion est active

## 5. Ouvrir le projet site-weco

1. Dans Claude Code Desktop, clique sur **Open project** ou **Ouvrir un projet**
2. Choisis **From GitHub** (ou « Depuis GitHub »)
3. Cherche `weco-coop/site-weco` dans la liste
4. Clique dessus, Claude télécharge le projet sur ton ordinateur
5. Quand c'est prêt, tu vois la liste des fichiers à gauche

Tu es prêt. Tout ce qui suit, tu peux le faire sans toucher au code, juste en parlant à Claude.

## 6. Faire une première modification

Pour t'entraîner, on va faire **trois petites modifs** : un texte, une photo, une couleur. À chaque fois, tu écris ta demande en français dans Claude, il fait le travail, tu valides.

### Exemple 1 : changer un texte

Tape simplement dans Claude :

> Sur le site, dans la section « Notre équipe », remplace « Marion » par « Marion D. »

Claude va chercher l'endroit, te montrer la modif, et la sauvegarder. Si le résultat te plaît, dis :

> Parfait, push sur GitHub avec le message « Mise à jour nom Marion »

### Exemple 2 : remplacer une photo

1. Mets la nouvelle photo sur ton bureau (au format .jpg ou .png)
2. Dans Claude, glisse-dépose le fichier dans la conversation
3. Écris :

> Remplace la photo de Romain dans la section équipe par cette image. Garde le même nom de fichier pour ne rien casser.

### Exemple 3 : changer une couleur

Le site utilise quelques couleurs précises (corail, jaune, violet). Pour changer une couleur, donne le code couleur si tu l'as, sinon décris :

> Le bouton « Nous contacter » est trop foncé, mets-le en corail clair, comme les titres.

Claude va te proposer un code couleur, te demander confirmation, puis appliquer.

## 7. Vérifier la preview sur GitHub Pages

Avant de publier sur le vrai site, on regarde toujours le résultat sur la **preview**. C'est une copie du site qui se met à jour automatiquement à chaque modif, mais que personne d'autre ne voit.

1. Va sur https://weco-coop.github.io/site-weco/
2. **Attends 1 à 2 minutes** après ton push (le temps que GitHub mette à jour)
3. **Recharge la page** (Ctrl+F5 sur Windows, Cmd+Shift+R sur Mac) pour voir la dernière version
4. Vérifie que ta modif est bien là et que rien d'autre n'a bougé

Si tout est bon, on passe à la publication. Sinon, redemande à Claude de corriger.

## 8. Publier sur weco.coop

C'est l'étape qui rend ta modif visible par tout le monde. **Elle est volontairement manuelle** : il faut cliquer un bouton, ça n'arrive jamais tout seul.

1. Va sur https://github.com/weco-coop/site-weco
2. Clique sur l'onglet **Actions** (en haut)
3. Dans la liste à gauche, clique sur **Déployer sur weco.coop**
4. Clique sur le bouton **Run workflow** (en haut à droite, gris)
5. Confirme avec **Run workflow** dans la petite fenêtre
6. Attends environ 1 minute, une coche verte apparaît
7. Va sur https://weco.coop, ta modif est en ligne

Si une croix rouge apparaît à la place de la coche : ne paniques pas, préviens Romain B. Il regardera ce qui a coincé.

---

## Ce qu'on peut modifier facilement

- **Textes** : tous les paragraphes, titres, légendes
- **Photos** : portraits équipe, photos de projets, logos partenaires
- **Couleurs ponctuelles** d'un bouton, d'un titre, d'un fond
- **Coordonnées** : adresse, téléphone, email
- **Liens** : ajouter ou changer un lien externe

## Ce qui demande précaution

Pour ces sujets, parles-en à Romain B. avant de demander à Claude :

- **Structure des sections** (en ajouter, en supprimer, en réorganiser)
- **Identité visuelle globale** (changer la palette, les polices)
- **Le menu de navigation**
- **Tout ce qui touche au fichier `index.html` en profondeur**
- **Les fichiers `sitemap.xml`, `robots.txt`, `.github/workflows/`**

Si tu touches à ces fichiers par erreur, pas grave : il suffit de revenir en arrière (voir FAQ).

## FAQ

**J'ai fait une bêtise, comment je reviens en arrière ?**
Dis simplement à Claude : *« Annule mon dernier changement »* ou *« Reviens à la version précédente du fichier index.html »*. Tant que tu n'as pas redéployé sur weco.coop, le vrai site n'a pas bougé. Et même si tu as redéployé, on peut toujours redéployer une version d'avant.

**La preview ne se met pas à jour, qu'est-ce que je fais ?**
Trois choses à essayer dans l'ordre :
1. Attends 2 minutes de plus (GitHub Pages est parfois lent)
2. Recharge la page en forçant : **Ctrl+F5** (Windows) ou **Cmd+Shift+R** (Mac)
3. Ouvre la page en navigation privée pour contourner le cache

Si après 5 minutes rien n'a bougé, vérifie sur GitHub que ton commit est bien arrivé (onglet « Code » du repo, regarde l'heure du dernier commit).

**Claude refuse de faire ce que je demande.**
Reformule plus précisément. Par exemple, au lieu de *« change la photo »*, dis *« dans la section équipe, remplace le fichier `photo-marion.jpg` par celui que je viens de glisser »*. Si Claude continue de refuser, c'est probablement qu'il a détecté un risque. Demande-lui *« pourquoi tu hésites ? »* avant d'insister.

**Le site est cassé après ma modif, qu'est-ce que je fais ?**
1. Ne re-déploie surtout pas une autre version par-dessus
2. Préviens Romain B. tout de suite
3. Précise ce que tu as modifié et l'heure

Si Romain n'est pas dispo, tu peux toi-même redéployer une version d'avant : sur GitHub, va dans **Actions → Déployer sur weco.coop**, clique sur la dernière exécution **réussie** (coche verte), et clique sur **Re-run all jobs**.

**Je ne vois plus le projet dans Claude Code.**
Vérifie que tu es bien connecté à GitHub dans les paramètres de Claude Code, et que l'accès à l'organisation `weco-coop` est toujours autorisé.

**Je peux travailler depuis mon téléphone ?**
Pas vraiment. Claude Code Desktop tourne sur ordinateur. Tu peux modifier directement sur github.com depuis le téléphone (clic sur un fichier, icône crayon), mais c'est moins confortable et plus risqué.

## Glossaire

- **GitHub** : le site qui héberge le code du projet. Comme un Google Drive, mais pour du code.
- **Repo** (ou repository) : un dossier projet sur GitHub. Le nôtre s'appelle `site-weco`.
- **Organisation** : un compte partagé sur GitHub qui regroupe plusieurs personnes et projets. La nôtre s'appelle `weco-coop`.
- **Commit** : une « sauvegarde » avec un petit message qui explique ce qui a changé. Chaque modif est un commit.
- **Push** : envoyer tes commits depuis ton ordi vers GitHub.
- **Branche** (branch) : une version parallèle du projet. On travaille tous sur la branche `main` pour l'instant, c'est plus simple.
- **Pull request** : une proposition de modif qu'on fait relire avant d'intégrer. On ne s'en sert pas pour l'instant.
- **Preview** : version de test du site, visible seulement avec son lien (`weco-coop.github.io/site-weco/`).
- **Production** : le vrai site, celui que tout le monde voit (`weco.coop`).
- **Actions** : la zone de GitHub où on déclenche les déploiements.
- **Workflow** : une recette automatique. Le nôtre s'appelle « Déployer sur weco.coop ».
- **Claude Code** : l'assistant IA qui modifie le code à ta place quand tu lui parles en français.

---

Tu es prêt. La règle d'or : **ne fais jamais une modif que tu ne comprends pas**, et **vérifie toujours la preview avant de publier**. Pour le reste, n'aies pas peur d'expérimenter, le système est fait pour pardonner.

Bonne prise en main, et bienvenue dans l'équipe qui fait vivre weco.coop.
