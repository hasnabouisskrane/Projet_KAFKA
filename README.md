# Projet_KAFKA

Apache KAFKA: Apache Kafka est une plateforme de streaming open source distribuée. Elle est souvent utilisée comme broker de messages, car elle propose des fonctionnalités similaires à une file d’attente de messages de publication/abonnement.

Tout d'abord, on doit démarrer les processus Kafka alors on va suivre les étapes de figure suivante:
-la première étape consiste à démarrer le service Zookeeper, puis à démarrer le serveur Kafka principal.
-Démarrez le service kafka


![35](https://user-images.githubusercontent.com/61788817/172738070-82d67eb8-ea14-47b4-ba69-6d03bf970bf8.PNG)

Après on va créer un simple producteur et un consommateur pour publier et s’abonner aux messages d’un sujet kafka. 

![34](https://user-images.githubusercontent.com/61788817/172738056-8f9571e8-465f-4911-8bd2-25d5d6d39ee1.PNG)

Un consommateur qui fait subscribe vers le topic R1
L'application a envoyé le message qui est par défaut sérialiser par format JSON.



![36](https://user-images.githubusercontent.com/61788817/172738087-62781382-66e5-4e64-b253-e3d2a0b362c0.PNG)

Maintenant on va créer un consumer dans une application spring boot dons on va envoyé un message via kafka console producer et on va voir est ce qu'il arrive au consumer, dans lequel on va créer des messages en format json; j'ai entré juste le nom et les autres paramètres sont gardé par par défaut.

![37](https://user-images.githubusercontent.com/61788817/172738103-58cc9f42-4367-4a54-85e2-ee8f1540f7f6.PNG)



![38](https://user-images.githubusercontent.com/61788817/172738110-e753aa3c-783d-44f4-8551-8f0f54a6cbb0.PNG)

Ensuite on créer un producer poller
Après on va lancer lancer un consommateur sur le topic R2, alors on va voir que les messages qui arrivent à chaque secondes qui indique que le supplier a bien fonctionner, le nome soit P1 ou P2 (probabilité de 50%) et aussi user soit U1 ou U2...

Mais si on a souhaité de régler o configurer au lieu d'une seconde on veut le mettre 2 secondes ou moins donc on va utiliser quelque paramètres dans le fichier application properties.
Donc dans la figure suivante pour chaque millisecondes les événements sont produit.


![40uuu](https://user-images.githubusercontent.com/61788817/172738315-95cd3c69-a6ec-416a-b174-a4ebb2ac1d63.PNG)


Si on veut testé manuellement on lit les résultats à partir de topic R1

![39](https://user-images.githubusercontent.com/61788817/172738132-377ae79c-30be-40c4-9f3b-57fa12b8de86.PNG)

Et si on veut analyser le flux des données en temps réel pour prendre des décisions donc on va utiliser KAFKA stream processing.
On va demander à kafka consumer d'afficher la clé et la valeur donc on utilise quelques options dans on va fait un commateur dans R4 

![img](https://user-images.githubusercontent.com/61788817/172863300-6ce1d31a-e797-4f7e-bc1c-291e5cefd03d.png)

Ensuite on va faire des statistiques sur une fenetre de temps pendant les cinqs dernieres secondes.
Dnas le console de consommateur  s'affiche les résultats temporelles de cinqs dernieres secondes(l'évolution=nombre de visite)


![41](https://user-images.githubusercontent.com/61788817/172738142-9e9d72ae-c599-4cd3-8f1e-580e7b440481.jpg)


Ici on reçoit un stream qui contient les résultats calculés(page et nombre de visite pour chaque seconde)


![42](https://user-images.githubusercontent.com/61788817/172738155-83c3e572-4f46-4ce1-8edc-af10e42db63c.jpg)


On peut exploiter les résultats dans une application web donc on a crée une page html et les résultats se présente sous forme des courbes


![43](https://user-images.githubusercontent.com/61788817/172738166-90a232a8-47df-4db3-974c-6101bce8f30d.jpg)












