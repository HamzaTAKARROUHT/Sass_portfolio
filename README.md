# Tutoriel SASS

Un site web sert à la fois d'exemple de projet SASS et de tutoriel pour apprendre SASS. Ce projet démontre une architecture modulaire, les bonnes pratiques et les fonctionnalités principales de SASS.

## Fonctionnalités

- Organisation modulaire des fichiers SASS
- Utilisation de variables et mixins
- Nesting et méthodologie BEM
- Design responsive
- Exemples de code interactifs
- Palette de couleurs interactive

## Structure du projet

```
projet/
├── scss/
│   ├── _variables.scss     # Variables globales
│   ├── _mixins.scss        # Mixins et fonctions
│   ├── _reset.scss         # Reset CSS
│   ├── components/         # Composants individuels
│   │   ├── _header.scss    # En-tête et navigation
│   │   ├── _button.scss    # Styles des boutons
│   │   ├── _card.scss      # Cartes de contenu
│   │   ├── _code-examples.scss  # Exemples de code
│   │   ├── _color-palette.scss  # Palette de couleurs
│   │   └── _lists.scss     # Styles de listes
│   └── main.scss           # Fichier principal qui importe tout
├── css/
│   └── main.css            # CSS compilé
└── index.html              # Page HTML
```

## Installation et compilation

### Prérequis

- Node.js et npm installés
- SASS installé globalement (`npm install -g sass`)

### Compilation

Pour compiler le SASS en CSS une seule fois :

```bash
sass scss/main.scss css/main.css
```

Pour compiler en continu et surveiller les changements :

```bash
sass --watch scss/main.scss:css/main.css
```

Pour la production (avec compression) :

```bash
sass scss/main.scss css/main.css --style compressed
```

## Concepts SASS démontrés

### Variables

```scss
$primary-color: #3498db;
$secondary-color: #2ecc71;
$spacing-unit: 8px;
```

### Nesting et BEM

```scss
.card {
  background-color: white;
  
  &__title {
    font-size: 20px;
  }
  
  &__content {
    margin-bottom: $spacing-unit * 2;
  }
}
```

### Mixins

```scss
@mixin button($bg-color, $text-color) {
  background-color: $bg-color;
  color: $text-color;
  // ...
}

.button--primary {
  @include button($primary-color, white);
}
```

### Responsive Design

```scss
@mixin responsive($breakpoint) {
  @if $breakpoint == tablet {
    @media (max-width: 768px) { @content; }
  } @else if $breakpoint == mobile {
    @media (max-width: 480px) { @content; }
  }
}
```

## Comment contribuer

1. Forkez le projet
2. Créez votre branche de fonctionnalité (`git checkout -b feature/amazing-feature`)
3. Committez vos changements (`git commit -m 'Add some amazing feature'`)
4. Poussez vers la branche (`git push origin feature/amazing-feature`)
5. Ouvrez une Pull Request

## Licence

Ce projet est sous licence MIT.

## Ressources additionnelles

- [Documentation officielle SASS](https://sass-lang.com/documentation/)
- [Introduction à BEM](https://css-tricks.com/bem-101/)
- [Architecture des projets SASS](https://www.sitepoint.com/architecture-sass-project/)