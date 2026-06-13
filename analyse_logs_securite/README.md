# Analyse de logs de sécurité

## Présentation
Dans ce projet, j’analyse un extrait de logs Linux liés au service SSH.

Le but est d’identifier ce qui semble normal, ce qui paraît suspect, et de formuler une première conclusion comme pourrait le faire un analyste SOC junior.

## Contexte
Un serveur Linux expose un accès SSH.  
Dans les logs, on observe plusieurs tentatives de connexion sur une courte période, puis une connexion réussie d’un utilisateur interne.

## Logs analysés
Les événements observés montrent :
- plusieurs échecs de connexion SSH
- une tentative sur des comptes sensibles
- une connexion réussie
- des commandes lancées avec `sudo`

## Ce que l’on remarque

### 1. Plusieurs échecs de connexion depuis la même adresse IP
L’adresse IP `185.243.115.84` revient plusieurs fois en quelques secondes.

Cela attire l’attention, car les tentatives sont rapprochées et répétées.

### 2. Les comptes visés sont très classiques
Les tentatives concernent les comptes :
- `admin`
- `test`
- `root`

Ce sont des noms souvent utilisés dans les attaques automatisées ou les essais de connexion opportunistes.

### 3. Les connexions échouent
On voit plusieurs lignes `Failed password`, puis une ligne indiquant que la connexion a été fermée avant authentification complète.

À ce stade, rien ne montre que cette adresse IP a réussi à se connecter.

### 4. Une connexion réussie apparaît ensuite
Un utilisateur nommé `analyste` se connecte avec succès depuis l’adresse IP `192.168.1.20`.

Cette adresse IP semble appartenir au réseau interne.  
Dans ce scénario, cette connexion paraît donc plus légitime que les précédentes.

### 5. L’utilisateur lance ensuite des commandes d’observation
Après sa connexion, l’utilisateur `analyste` utilise `sudo` pour exécuter :
- `cat /var/log/auth.log`
- `ss -tulnp`

Ces commandes peuvent correspondre à une vérification du système après les tentatives de connexion observées.

## Analyse
L’ensemble des logs laisse penser à une tentative de brute force ou à une série d’essais automatisés sur le service SSH.

Les éléments qui vont dans ce sens sont :
- plusieurs tentatives rapprochées
- une même adresse IP externe
- plusieurs comptes testés
- l’usage de comptes classiques comme `admin` et `root`

En revanche, je ne vois pas ici de preuve claire d’une compromission réussie par l’adresse IP externe.

## Conclusion
L’activité observée est **suspecte** et ressemble à une **tentative probable de brute force SSH**.

À ce stade :
- une activité malveillante est probable
- aucune compromission n’est confirmée dans cet extrait
- une surveillance renforcée reste nécessaire

## Recommandations
- Surveiller ou bloquer l’adresse IP `185.243.115.84`
- Vérifier si d’autres serveurs ont reçu les mêmes tentatives
- Renforcer la surveillance des journaux SSH
- Mettre en place une protection comme Fail2ban
- Désactiver l’authentification par mot de passe si possible
- Privilégier l’authentification par clé SSH
- Limiter les accès distants aux comptes sensibles

## Compétences travaillées
- Analyse de logs Linux
- Détection d’activité suspecte
- Identification d’une tentative de brute force
- Triage initial
- Rédaction d’un compte rendu simple
