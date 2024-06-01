# DevOps23_24

5. Exécuter un serveur web (apache, nginx, ...) dans un conteneur docker

a. Récupérer l'image sur le Docker Hub 

Lien Docker Hub, j'ai opter pour apache : https://hub.docker.com/_/httpd

b. Vérifier que cette image est présente en local 

METTRE IMAGE

c. Créer un fichier index.html simple 

METTRE IMAGE

d. Démarrer un conteneur et servir la page html créée précédemment **à l'aide d'un volume** (option -v de docker run)

commande utilisé : docker run -d -p 8080:80 -v /home/jean/DevOps23_24/html/index.html:usr/local/apache2/htdocs/index.html httpd:2.4

e. Supprimer le conteneur précédent et arriver au même résultat avec la commande **docker cp**

pour supprimer le conteneur : sudo docker container rm <identifiant_container>

pour run le conteneur httpd en daemon : sudo docker run -d -p 8080:80 --name my_apache_server httpd

pour copier le fichier demandé dans un docker qui est entrain de run : sudo docker cp /home/jean/DevOps_2324/html/index.html my_apache_server:/usr/local/apache2/htdocs/index.html

6. Builder une image

a. A l'aide d'un dockerfile, crée une image (commande docker build)

b. Exécuter cette nouvelle image de maniére à servir la page html (commande docker run)
 
c. Quelles différences observez-vous entre les procédures 5. et 6. ? 

Les deux pour moi permettent différente utilisation en fonction du stade ou l'on se trouve. La méthode 5. est plus adapté pour du "test" c'est à dire on run notre container et on lui balance au fur et à mesure et selon nos besoin les fichiers pour voir un peu l'intéraction en direct les changements etc...
Tandis que la méthode 6. avec une image(dockerfile) me fait beaucoup plus penser à une méthode de production, on a finis de tester on connait les étapes dont on a besoin on les inscrits dans l'image afin d'éviter toute erreur qui ont été essayer durant l'utilisation de la méthode 5.

7. Utiliser une base de données dans un conteneur docker

a. Récupérer les images mysql:5.7 et phpmyadmin depuis le Docker Hub

b. Exécuter deux conteneurs à partir des images et ajouter une table ainsi que quelques enregistrements dans la base de données à l'aide de phpmyadmin
(Je me suis aidé de ChatGPT pour cette partie)

Créer un network de container afin de permetter à phpmyadmin et mysql de communiquer

METTRE IMAGE

Lancer les deux conteneurs dans le network

METTRE IMAGE

Ensuite accéder à phpmyadmin (via le port 8081)

METTRE IMAGE

Et se login et créer une table et insérer une valeur

METTRE IMAGE
