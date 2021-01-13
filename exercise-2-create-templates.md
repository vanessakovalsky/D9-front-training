# Exercice 2: Création de templates:

Cet exercice a pour objectif de nous faire créer les différents templates nécessaire à notre site.
Pour cela nous utiliserons les maquettes présentes ici : https://app.moqups.com/yNkQ7nytUR/view/page/aa9df7b72  

## Créer un template pour les noeuds bateaux
* Dans le dossier template, créer un fichier node--bateau.html.twig dans un dossier node qui permet de définir la mise en page de tous les contenus de type bateau
* Celui-ci contient le code suivant :

```

{%
  set classes = [
    'node',
    'node--type-' ~ node.bundle|clean_class,
    node.isPromoted() ? 'node--promoted',
    node.isSticky() ? 'node--sticky',
    not node.isPublished() ? 'node--unpublished',
    view_mode ? 'node--view-mode-' ~ view_mode|clean_class,
  ]
%}
node bateau
{{ attach_library('classy/node') }}
<article{{ attributes.addClass(classes) }}>

  {{ title_prefix }}
  {% if label and not page %}
    <h2{{ title_attributes }}>
      <a href="{{ url }}" rel="bookmark">{{ label }}</a>
    </h2>
  {% endif %}
  {{ title_suffix }}

  {% if display_submitted %}
    <footer class="node__meta">
      {{ author_picture }}
      <div{{ author_attributes.addClass('node__submitted') }}>
        {% trans %}Submitted by {{ author_name }} on {{ date }}{% endtrans %}
        {{ metadata }}
      </div>
    </footer>
  {% endif %}

  <div{{ content_attributes.addClass('node__content') }}>
    {{ content }}
    <div class="bateau-proprietaire">
    Proprietaire :
    <img src="{{ file_url(node.field_proprietaire.0.entity.user_picture.entity.uri.value) }}">

    Nom : {{ node.field_proprietaire.0.entity.field_nom.0.value }}
    Prénom : {{ node.field_proprietaire.0.entity.field_prenom.0.value }}
    </div>
  </div>

</article>
```

## Créer un template pour la page d'accueil et la vue
* A l'aide du debuggueur, trouver les fichiers de template à créer et leur contenu de base pour 
* * la page d'accueil
* * la vue Mes bateaux 
* Créer ses fichiers et définirs les templates associés pour correspondre à la maquette