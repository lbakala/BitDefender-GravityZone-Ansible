# BitDefender-GravityZone-Ansible

Gestion d'un parc des clients end-point de bout en bout

Gravityzone est une solution de securité pour les entreprises. Elle permet de protéger plusieurs machines.

La solution necessite un centre de controle et les machines à protéger.

Le Centre de controle peut être installer en local : version on premise

Ou dans le Cloud : version Cloud

Toutes les machines à protéger doivent disposer du client end point favorisant les échanges avec le centre de controle.

                            +------------------------+
				|                        |
				|   Centre de controle   | 
				|                        |
				+------------------------+
                                          |
                                          |
        +-----------------+---------------+----------------+-------------------------------------------------> ...n  
        |                 |               |                |
        |                 |               |                | 
        +-----------+     +-----------+   +-----------+    +-----------+     
        |           |     |           |   |           |    |           |
        |    SRV1   |     |    SRV2   |   |    SRV3   |    |    SRV4   |    
        |           |     |           |   |           |    |           |
        +-----------+     +-----------+   +-----------+    +-----------+

 **Notre Premier objectif est d'automatiser la gestion des serveurs à protéger suivant les opérations :**
 
 - Installation du client en point
 - Vérification de l'état des mises à jour
 - Lancement de mises à jour manuelle
 - Ouverture de tickets de demande d'assistance au support BitDefender en joigant les logs concernés
 
 **Le deuxième d'exposer les problématiques rencontrées après le deploiement**
 
 - Résolution de noms de serveur BitDefender
 - Incompatibilité Debian 8
 
 ## I - Obtention de la licence BitDefender
 
 En remplissant le formulaire accessible à l'adresse : https://www.bitdefender.fr/business/free-trials/, 
 
 vous obtiendrez une licence de 30 jours.
 
 ## II - Accès au centre de controle et téléchargement des binaires d'installation
  
  Suite à la demande effectuer précedemment, vous recevrez dans l'email fourni deux courriers de bitDefender Gravityzone :
  
  - le premier contient la clé de la licence
  - le deuxième contient l'adresse url d'accès au centre de contrôle, suivi du login et le mot de passe.
  
  Accéder au centre de contrôle en acceptant les termes de licence
  
  - Allez dans package dans le menu à Gauche
  - Cliquez sur le boutton ajouter 
  - Entrez un nom pour cette configuration des packages
  - Personnalisez vos packages en fournissant les informations propres à votre configuration si besoin et enregistrer
  
 C'est fait, vous venez de créer une base de téléchargement des packages personnalisés.
 
 Pour télécharger les binaires d'installation, 
 
 - Faites un clique droit sur l'élément présent dans packages que vous avez créé.
 - Téléchargez les binaires souhaités ou envoyer un lien de téléchargement par mail
 
 ## III - Deploiement de BitDefender End Point Security Tools
 
 Voici les étapes à suivre le deploiement sur une machine.
       
       root@small:/tmp# tar -xvf installer.tar
       root@small:/tmp# chmod +x installer
       root@small:/tmp#  ./installer
       
 Vous vous imaginez faire cette manipulation sur un parc de 10000 machines ?
 
 - Recupérer l'archive de plus 600 MB via scp sur chaque serveur
 - Décomprésser installer.tar  et modifier les droits du fichier installer
 - Lancer l'installation
 
 
 
 

 
  
    
  
