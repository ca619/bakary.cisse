# Analyse d'incident

## Résumé

L’entreprise a subi un incident de sécurité lorsque l’ensemble des services réseau a cessé de répondre.  
L’équipe cybersécurité a déterminé que la perturbation avait été causée par une **attaque DDoS via un flot de paquets ICMP entrants**.

Pour contenir l’incident, l’équipe a bloqué le trafic malveillant, arrêté les services non critiques et restauré les opérations réseau essentielles.

---

## Identifier

Un acteur malveillant a ciblé l’entreprise avec une **attaque par inondation ICMP**.  
L’ensemble du réseau interne a été affecté, rendant plusieurs services indisponibles.

L’enquête a montré qu’un **pare-feu mal configuré** avait permis à l’attaquant de saturer le réseau avec du trafic ICMP.

---

## Protéger

Pour renforcer la protection contre ce type d’attaque, l’entreprise a mis en place :

- une nouvelle règle de pare-feu limitant le nombre de paquets ICMP entrants,
- une solution IDS/IPS chargée de filtrer le trafic ICMP suspect.

Ces mesures réduisent l’exposition aux attaques par déni de service et améliorent la défense périmétrique.

---

## Détecter

Pour améliorer les capacités de détection, l’entreprise a ajouté :

- une vérification de l’adresse IP source sur le pare-feu,
- un logiciel de surveillance du réseau pour détecter les schémas de trafic anormaux.

Ces contrôles permettent de mieux repérer le trafic usurpé et de détecter plus rapidement une activité réseau suspecte.

---

## Réagir

Pour les futurs incidents, le processus de réponse doit inclure :

- l’isolement des systèmes affectés si nécessaire,
- la restauration prioritaire des services critiques,
- l’analyse des journaux réseau,
- l’escalade vers la direction,
- la notification des autorités compétentes si besoin.

Une procédure documentée permet de réduire le temps de réaction et d’améliorer la coordination.

---

## Rétablir

Pour rétablir le fonctionnement après ce type d’attaque, l’entreprise doit :

- restaurer les services réseau jusqu’à un état normal,
- maintenir hors ligne les services non critiques jusqu’à stabilisation,
- remettre en service d’abord les systèmes critiques,
- revoir et améliorer les procédures de reprise après incident.

Cela permet d’assurer la continuité d’activité et d’augmenter la résilience face à des incidents similaires.

---

## Points clés à retenir

- Une mauvaise configuration de sécurité peut exposer le réseau à une interruption de service.
- Une attaque par inondation ICMP peut rapidement affecter la disponibilité du réseau interne.
- Le durcissement du pare-feu, l’IDS/IPS et la surveillance réseau sont essentiels.
- Le NIST CSF fournit une structure claire pour analyser l’incident et améliorer la posture de sécurité.
