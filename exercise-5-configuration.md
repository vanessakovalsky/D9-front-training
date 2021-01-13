# Exercice 5 - Gestion de la configuration

Cet exercice a pour objectifs :
* de créer une configuration de formats d'image
* d'exporter cette configuration pour qu'elle soit installée lors de l'installation du thème

## Créer des formats d'image:
* Dans l'administration allez dans Configuration > Media > Styles d'images
* Crééer deux nouveaux style d'image avec les noms et taille suivantes :
* * Home : 500px X 800px
* * Icone: 40 X 40px

## Exporter la configuration
* Depuis le menu Configuration > Synchronisation,  exporter la configuration des formats d'images créés dans des fichiers yml (ou le faire avec drush ou la drupal console)
* Supprimer les UUID des fichiers et mettre les fichiers dans le theme dans le dossier montheme/config/optionnal

## Tester les nouvelles configurations
* Dans l'administration supprimer les formats d'images créés
* Réinstaller le theme
* Vérifier que les formats d'images soient bien importés

-> Félicitations vous savez embarquez de la configuration dans votre thème.