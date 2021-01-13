# Exercice 3 - Association de feuille de style

Cet exercice a pour objectif :
* de vous faire définir la structure de vos feuilles de styles en respectant l'architecture SMACSS
* d'associer vos feuilles de styles à votre thème pour pouvoir les utiliser

## Définition de l'architecture des feuilles de styles
* En respectant l'architecture SMACSS définir l'architecture des feuilles de styles de votre thèmes 
* Créer l'arborescence et les fichiers correspondants 
* Définir quelques règles CSS pour rendre le rendu propre et agréable à l'oeil.

## Déclaration des fichiers en tant que bibliothèque de votre thème
* Dans le fichier montheme.libraries.yaml, dans la section global, il est nécessaire de déclarer les différents fichier, comme dans l'exemple ci-dessous (à adapter en fonction de votre architecture de fichiers)
```
global:
  js:
    js/demotheme.js: {}
  css:
    base:
      css/base/elements.css: {}
    component:
      css/components/block.css: {}
      css/components/breadcrumb.css: {}
      css/components/field.css: {}
      css/components/form.css: {}
      css/components/header.css: {}
      css/components/menu.css: {}
      css/components/messages.css: {}
      css/components/node.css: {}
      css/components/sidebar.css: {}
      css/components/table.css: {}
      css/components/tabs.css: {}
      css/components/buttons.css: {}
    layout:
      css/layouts/layout.css: {}
    theme:
      css/theme/print.css: { media: print }
```    
* N'oublier pas d'inclure dans vos templates les fichiers CSS dont vous avez besoin avec la fonction attach_library
```
{{ attach_library('classy/node') }}
```

-> Félicitations vous savez architecturer vos fichiers, les déclarer et les utiliser dans vos templates, il ne vous reste plus qu'à paufiner les templates et feuilles de style pour rendre l'affichage plus attrayant 