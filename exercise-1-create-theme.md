# Exercice 1- Création d'un thème

Cette série d'exercices a pour objectif de nous faire créer les différents templates nécessaire à notre site.
Pour cela nous utiliserons les maquettes présentes ici : https://app.moqups.com/yNkQ7nytUR/view/page/aa9df7b72  

Cet exercice a pour objectif :
* d'activer le debug
* de créer son premier thème

## Pré-requis 
* Installer un drupal vierge : https://www.drupal.org/docs/installing-drupal 
* Télécharger et installer le module boatmanagement qui se trouve à 
cette adresse : https://github.com/vanessakovalsky/D8-dev/tree/master/boatmanagement 
-> Cela vous permettra d'avoir la configuration faite et la structure de données
 pour réaliser le template de ce TP.


##  Activer le debug de Twig : 
* Dans sites/default copier le fichier default.services.yml en services.yml
* Dans le fichier services.yml faites les modifications suivante dans la config twig : 
* * debug: true
* * auto_reload: true
* * cache: false
* /!\ cela désactive uniquement le cache de twig mais certains fichiers reste mis en cache par drupal.
* Pour désactiver le cache de drupal complètement : 
* * Dans sites copier le fichier example.settings.local et renommer la copie en settings.local
* * Dans le settings.php décommenter les lignes suivantes :
```
if (file_exists($app_root . '/' . $site_path . '/settings.local.php')) {
  include $app_root . '/' . $site_path . '/settings.local.php';
}
```

## Créer votre premier thème

* Avec l'aide de la console, générer un thème qui s'appuie sur le thème parent Classy
```

```
* Modifier les regions du thèmes présents dans le montheme.info.yml pour ne laisser que les région suivante :
* * Header
* * Content
* * Sidebar
* * Footer
* * Menu
* * Breadcrumb


* Avec l'aide du debugguer de twig pour trouver le template utiliser,
trouver le template de la page qui déclare les régions, dupliquer le dans votre 
dossier template de votre thème et supprimer les régions inutiles

-> Félicitation vous savez créer un thème et activer le mode debug pour faciliter vos développements