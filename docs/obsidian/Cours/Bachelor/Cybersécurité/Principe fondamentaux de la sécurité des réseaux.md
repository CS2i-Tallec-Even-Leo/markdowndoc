
# Menace et failles/vulnérabilité de sécurité - Les menaces

## vol d'information

Consiste à obtenir des informations confidentielles afin de les revendre ou de les exploiter (guerre économique et industrielle )
## Perte et manipulation de données

Consiste à accéder à des informations pour les détruire ou les modifier.


## Usurpation d'identité 

Consiste à utiliser des informations relatives à un tiers afin de se faire passer pour lui.

## Interruption de Service

Consiste à interdire aux utilisateurs légitimes l’accès à leurs services. Exemple attaques DoS {Deny of Service}.



## 3 grande familles de vulnérabilité

- Failles technologiques {technological vulnerability} .
	- Protocoles qui n'ont jamais été pensés en terme de sécurité (IP,TCP,UDP,ICMP,SNMP,HTTP,FTP)
	- Systèmes d'exploitation qui doivent être régulièrement mis à jour et qui ne sont pas toujours configurés avec des mots de passe forts.
	- Equipements réseau qui ne sont pas toujours configurés avec des mots de passe forts et dont le système d'exploitation doit être régulièrement mis a jours 
	- la Tendance de plus en plus marqué à l'auto configuration rend les réseaux de plus e, plus sensibles aux attaques qui s'appuient sur les protocoles prévus à cet effet 
- Failles de configuration {configuration vulnerability}. 
	- Compte utilisateur et systeme mal protégés par des mots de passe faibles ou trop prévisible ainsi que des noms d'utilisateurs trop accessible 
	- Service mal configurés et activations de scripts non justifiées.
	- Parametres par défaut non modifiés
	- Erreurs de configuration des protocoles et périphériques réseaux (protocoles de routage, protocoles de découvertes, liste de contrôle d’accés, …).
- Failles de stratégie {policy vulnerability}.
	- Stratégie de sécurité absente ou non formalisée
	- Probleme structurels de l'organisation(défiance entre services,mauvais communications)
	- Mauvaise stratégie de mots de passe.
	- Pas ou peu de contrôle des accès ou du trafic.
	- Non respect de la stratégie de sécurité (Installations matérielles ou logicielles non conforme)
	- Pas de plan de reprise d’activité suite à sinistre : PCA {Plan de Continuation d’Activité) et/ou PRA {Plan de Reprise d’Activité} absents.


## Solutions

CERT ( Computer Emergency Response Team) recensent les failles technologiques
cependant ce nom est déposé on utilisera donc 

il devient préférable d'utiliser le terme CSIRT (Computer Security Incident Response Team)

En France l'ANSI

# Différent type d'attaque 


## Malware : 

Mot valise : Malicious Software {logiciel malveillant}
Ensemble de programmes conçu par un pirate pour être implanté dans un system  afin d'y déclencher une opération non autorisée ou d'en perturber le fonctionnement.

## Virus

Logiciel malveillant, généralement de petite taille, qui se transmet par les réseaux ou les supports d'information amovibles, s'implante au sein des programmes en les parasitant, se duplique à l'insu des utilisateurs et produit ses effets dommageables quand le programme infecté est exécuté ou quand survient un évènement donné.

## VERS 

Contrairement au virus, le ver ne s'implante pas au sein d'un autre programme. 2. Les vers sont souvent conçus pour saturer les ressources disponibles ou allonger la durée des traitements. Ils peuvent aussi détruire les données d'un ordinateur, perturber le fonctionnement du réseau ou transférer frauduleusement des informations. Un ver peut produire des effets soit immédiatement soit de manière différée (à une date donnée, lors de la survenue d'un évènement ou par déclenchement d'une bombe programmée). 3. Bien qu'ils s'en distinguent, les vers sont parfois appelés « virus »

## Trojan 

Logiciel apparemment inoffensif, installé ou téléchargé et au sein duquel a été dissimulé un programme malveillant qui peut par exemple permettre la collecte frauduleuse, la falsification ou la destruction de données. Équivalent étranger : Trojan horse (en) 


Attaque de reconnaissance {Reconnaissance attack} : 
- Requêtes Internet {Internet Query}. 
- Moteurs de recherche 
- Réseaux sociaux -
- Whois 
- … 
Balayage Ping {Ping Sweep}.
Balayage de ports {Port Scans}

- Attaque de mot de passe : 
	- Attaque en force {Brute force attack} 
	- Attaque par table Arc en ciel {Rainbow table attack} 
	- Attaque par chevaux de Troie {Trojan horse attack}
	- Analyse des paquets {Packet sniffing attack}
	
Attaque de confiance {Trust exploitation}. 
Attaque par redirection de port {Port redirection attack}. 

	Il s’agit d’une attaque rebond. Le pirate prend le contrôle d’un hôte compromis à partir duquel il exécute des requêtes sur la cible

Attaque de l'homme du milieu {Man-in-the-Middle attack}

	L’attaquant s’insère dans la communication entre la source et le destinataire et modifie/vole les données de la source, La source et le destinataire peuvent âtre un utilisateur ou une application.


## Atténuation des attaques {Attack Mitigation} :

défense en profondeur L’approche de défense en profondeur du réseau met en œuvre de périphériques de sécurité qui travaillent de concert : 
- VPN 
- Pare-feu. 
- Système de prévention d’intrusions {Intrusion Prevention System, IPS} : surveille les flux entrant et sortant et bloque les menaces dès leur détection. 
- Appareil de sécurité de messagerie {E-mail Security Appliance, ESA} : filtre les courriels suspects et les spams. 
- Appareil de sécurisation du WEB {WEB Security Appliance, WSA} : filtre les sites WEB. 
- Serveur AAA (authentification autorisation audit) qui centralise une base de données d’authentification d’utilisateurs et d’attribution de droits aux utilisateurs.

### Atténuation des attaques : Les sauvegardes 

Il existe trois types de sauvegardes : 
- Sauvegardes complètes qui prennent beaucoup de temps. 
- Sauvegardes différentielles : sauvegardes de tout ce qui a été modifié depuis la dernière sauvegarde complète. 
- Sauvegardes incrémentielles : sauvegardes de tout ce qui a été modifié depuis la dernière sauvegarde (complète ou pas). 
Le choix entre ces type de sauvegardes est fonction du temps disponible pour réaliser la sauvegarde (fenêtre de sauvegarde) et le temps désiré de restauration.

### Atténuation des attaques : Pare-feu 

Caractérisation des pares-feux : 
- Filtrage de paquets: les règles sont basées sur les adresses IP.
- Filtrage des applications : les règles sont en plus basées sur les numéros de ports
- Filtrage des URLs : Les règles s'appuient sur des catégorie et sous catégories de sites.
- Inspection minutieuse des paquets {Stateful Packet Inspection} : la réponse à une requête autorisée est automatiquement acceptée.
Ce n'était pas le cas avec les premiers pares-feux.
