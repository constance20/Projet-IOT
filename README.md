        # Projet-IOT

    Rapport d’IoT
Sujet du Projet
Pour le cours d’Internet des Objets nous avons dû imaginer une “Station Météo Connectée”, à placer par exemple dans un logement afin de recueillir tout type de données météorologiques.

    Choix technologique
Pour la station, nous avons imaginé à la suite des cours que la communication se ferait par Wi-Fi en choisissant un protocole MQTT. Notre choix s’est porté sur le MQTT car c’est une technologie relativement simple d’utilisation et il nous semblait plutôt adapté. En effet, la souscription à différents topics est flexible, et on peut aussi gérer plusieurs clients assez facilement ; les publishers envoient les données, les subscribers les reçoivent, le serveur n’est qu’une passerelle. Ainsi, par le transit des données via le serveur, les publishers et subscribers seraient donc indépendants.

On peut traduire cette récupération des données via un affichage graphique qui serait codé en utilisant du VueJS.

Dans l’idée, il faut via Python demander la météo pour une ville donner par retour par Open Weather API base_url = “http://api.openweathermap.org/data/2.5/weather?” api_key = “7d5cb654527b774dadb9ad3b92045cdb” qui communique par la suite avec le MQTT et un arduino afin d’obtenir les informations souhaitées, qui seront retranscrites via un tableau et/ou un graphique.

    << How to >>
Serveur Mqtt pour le broker sous mosquitto Adresse du serveur : 192.168.43.79 Port : 1883 Attention, a executer en admin - Démarrer le Serveur mosquitto.exe -c mosquitto.conf -v - Subscribe manuellement à un ou plusieurs topics mosquitto_sub.exe -t - Publish manuellement à un topic mosquitto_pub.exe -t -m - Editer la config mosquitto.conf: listener 1883 0.0.0.0 listener 61614 protocol websockets

Capteur de température Arduino :

Connexion au broker Mqtt en WiFi (Esp8266) Emission sur le topic: Temperature extérieure
Récupération des données du capteur local
Scripts Python Récupération des données via le web via Requetes HTTP

    Usages potentiels
Pour cette station météorologique connectée, en plus du relever de la température on peut imaginer les fonctions suivantes :

+ Humidité
+ Vent
+ Levée du soleil
+ Coucher de soleil
+ Description du ciel (s'il fait nuageux, etc)
