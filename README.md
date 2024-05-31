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

