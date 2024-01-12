Dans un fichier Docker Compose YAML, les ports sont spécifiés sous la clé `ports`. Cette clé permet de définir les ports à exposer sur le conteneur Docker et de les mapper vers des ports sur l'hôte. La syntaxe générale pour spécifier les ports dans un fichier Docker Compose est la suivante :

```yaml
services:
  nom_du_service:
    image: nom_de_l_image
    ports:
      - "port_hote:port_conteneur"
```

Explication des éléments :
- `nom_du_service`: Il s'agit du nom du service pour lequel vous configurez les ports.
- `nom_de_l_image`: C'est le nom de l'image Docker à utiliser pour ce service.
- `ports`: C'est la clé où vous spécifiez les ports à exposer.
- `"port_hote:port_conteneur"`: Cette syntaxe indique le mappage des ports. Le port sur l'hôte est à gauche des deux points, et le port dans le conteneur Docker est à droite des deux points. Vous pouvez également spécifier seulement le port de l'hôte pour laisser Docker choisir un port disponible dynamiquement sur l'hôte.

Exemple concret :

```yaml
services:
  webapp:
    image: nginx:latest
    ports:
      - "8080:80"
```

Dans cet exemple, le service "webapp" utilise l'image Nginx et expose le port 80 à l'intérieur du conteneur vers le port 8080 sur l'hôte.

Notez que le mapping de ports est essentiel pour permettre aux applications à l'intérieur des conteneurs Docker d'être accessibles depuis l'extérieur du conteneur, par exemple, lorsque vous souhaitez accéder à une application web hébergée dans un conteneur depuis votre navigateur.
