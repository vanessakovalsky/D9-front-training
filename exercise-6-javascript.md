# Exercice 6 - Javascript

Cet exercice a pour objectifs : 
* D'utiliser une librairie JS
* de créer ses propres fichiers JS 
* de les utiliser lorsque c'est nécessaire

## Import de la librairie et création du fichier JS 
* A partir de l'url, https://nnattawat.github.io/flip/ installer la librairie, dans vendor/flip 
* Créer un script js dans le theme dans montheme/js/ . Celui contient :
```js
(function ($, Drupal) {
    'use strict';
    $(document).ready(function(){
        $('.block-flipblock').flip();
    });
    } (jQuery, Drupal));  
```
* Ce script doit permettre le comportement des flipbox (afficher la description au survol de la souris)

## Déclaration de la librairie et utilisation dans un template
* Il est nécessaire de déclarer le fichier JS sous forme d'une librairie dans les librairies du thème.
* Ajouter dans le fichier montheme.librarires.yml les lignes suivantes :
```yml
flipblock:
  js:
    vendor/flip/jquery.flip.min.js: {}
    js/flip.js: {}
  dependencies:
    - core/jquery
```
* Créer un fichier template dans templates/block/block--flip.block.html.twig avec le code suivant :
```html
{%
  set classes = [
    'block',
    'block-' ~ configuration.provider|clean_class,
    'block-' ~ plugin_id|clean_class,
    'col-3',
    'block-flipblock',
  ]
%}
{{ attach_library('demotheme/flipblock') }}
<div{{ attributes.addClass(classes) }}>
  {{ title_prefix }}
  {% if label %}
    <h2{{ title_attributes }}>{{ label }}</h2>
  {% endif %}
  {{ title_suffix }}
  {% block content %}
    <div class="front">
      {{content.field_icone_flib}}
    </div>
    <div class="back">
      {{ content.body }}
    </div>
  {% endblock %}
</div>
```

-> Félicitations, vous savez maintenant attacher une bibliothèque JS et déclarer vos propres bibliothèques.