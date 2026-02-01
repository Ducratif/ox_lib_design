# Design Simple pour **ox_lib** (CSS Only)

Un petit *theme* CSS “plug & play” pour uniformiser le style des menus **ox_lib** (Mantine) avec un look sombre + accent bleu.

> ✅ Ce dépôt ne contient **que** un fichier CSS (pas le script complet) afin de respecter les droits / licences.  
> ✅ Compatible avec les builds classiques de **ox_lib** (UI compilée dans `web/build/`).

---

## Aperçu

- Fond sombre semi-transparent
- Bordure bleue autour des menus
- Boutons “en blocs séparés”
- Hover bleu + léger déplacement
- Icônes bleues
- Fix de fond Mantine (ScrollArea)
<br><br><br>
![Aperçu](./ox_lib_redesign.gif)
<br><br><br>

---

## Installation

### 1) Ajouter le fichier CSS

Crée (ou copie) ton fichier CSS ici :

```
web/build/assets/custom1.css
```

> Le nom `custom1.css` est **libre** : tu peux le renommer (ex: `customv1.css`, `theme_ducratif.css`, etc.).  
> Si tu le renommes, pense à adapter le lien dans le `index.html`.

---

### 2) Lier le CSS dans le HTML

Ouvre :

```
web/build/index.html
```

Repère la ligne (le hash varie selon les builds) :

```html
<link rel="stylesheet" crossorigin href="./assets/index-BgkLwDpx.css">
```

Ajoute **juste après** ton fichier CSS custom :

```html
<link rel="stylesheet" crossorigin href="./assets/customv1.css">
```

✅ Exemple complet :

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/src/favicon.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>NUI React Boilerplate</title>

    <script type="module" crossorigin src="./assets/index-Dk9MkoH6.js"></script>

    <link rel="stylesheet" crossorigin href="./assets/index-BgkLwDpx.css">
    <link rel="stylesheet" crossorigin href="./assets/customv1.css">
  </head>
  <body>
    <div id="root"></div>
  </body>
</html>
```

---

## Modifier le thème

Le fichier est volontairement simple : tu peux tout ajuster très vite.

### Changer la couleur principale (bleu)

Cherche la couleur `#008CFF` et remplace-la par la tienne.

Exemples :
- Rouge : `#ff2b2b`
- Violet : `#8b5cf6`
- Vert : `#22c55e`

---

### Rendre le menu plus “rond” (arrondis)

Cherche `border-radius` dans le bloc du conteneur (le menu) et dans le bloc des items (boutons).  
Augmente la valeur pour arrondir davantage.

Exemples :
- `4px` (léger)
- `8px` (moyen)
- `12px` (très arrondi)

---

### Rendre le menu plus opaque / plus transparent

Ajuste les valeurs `rgba(...)` :

- **Fond du menu** : `rgba(15, 15, 15, 0.90)`
- **Fond des boutons** : `rgba(40, 40, 40, 0.6)`
- **Fond hover** : `rgba(0, 140, 255, 0.25)`

Le dernier nombre = l’opacité (**0.0 → 1.0**).

---

### Espacement entre les boutons

Le style “blocs séparés” dépend surtout de :

- `margin-bottom: 6px;` (espace entre items)
- `padding: 8px;` (padding du conteneur)
- `border: 1px solid ...` (délimitation des blocs)

---

### Désactiver l’effet “déplacement” au survol

Si tu ne veux pas le petit “pop” au hover, supprime ou mets à `0` :

- `transform: translateX(3px);`

---

## Notes importantes

### Hash du fichier index-XXXX.css
Le nom `index-BgkLwDpx.css` est généré par le build et **change** souvent.  
C’est normal : tu n’as rien à modifier dedans, il te sert juste de repère pour insérer ton lien custom.

### Après update d’ox_lib
Quand tu mets à jour **ox_lib**, le dossier `web/build/` peut être remplacé.  
➡️ Pense à **réappliquer** :
- ton fichier CSS dans `web/build/assets/`
- ta ligne `<link ... custom...>` dans `web/build/index.html`

---

## Dépannage

- **Le thème ne s’applique pas**
  - Vérifie que le chemin du fichier est bon : `web/build/assets/…`
  - Vérifie le nom dans le `<link>` (il doit correspondre exactement)
  - Fais un redémarrage / clear cache si nécessaire

- **Certains menus ne changent pas**
  - ox_lib utilise Mantine : selon les composants, certaines classes peuvent varier.
  - Tu peux ajouter des sélecteurs supplémentaires en gardant la même logique.

---

## Compatibilité

- **ox_lib** (UI Mantine)  
- Fonctionne tant que les classes Mantine ciblées existent (menus / hovercards / dialogs / items).

---

## Licence / crédits

Design CSS : **Ducratif | DucraShop**  
Ce dépôt distribue uniquement le CSS et ne fournit aucun fichier propriétaire de **ox_lib**.

---

## Discord

➡️ Rejoins le Discord:
- `https://discord.gg/kpD8pQBBWm`

---

## Support

Si tu as un menu qui n’est pas pris en compte, envoie :
- une capture du menu
- la version de ox_lib
- ton `custom*.css`

Je te dirai exactement quel sélecteur ajouter.
