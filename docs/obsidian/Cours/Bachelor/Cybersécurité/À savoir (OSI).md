## Le modèle OSI (Open System Interconnection)

### Couche 1 : Physique

**Fonction :** Transmission d'une suite de bits

**PDU :** Suite de bits

**Encapsulation :** Conversion des bits en signaux électromagnétiques

**Équipements :** câbles (cuivre, fibre), bluetooth, concentrateurs (hubs)

### Couche 2 : Liaison de données

**Fonction :** Organise les bits en trames et les transmet. Sous-couches MAC et LLC.

**PDU :** Trames

**Encapsulation :** Ajoute des en-têtes et des pieds de pages aux trames

**Équipements :** Commutateur (switch) et pont réseau (bridge)

### Couche 3 : Réseau

**Fonction :** Routage, transfert et adressage sur un réseau

**PDU :** Paquets

**Encapsulation :** Ajoute des en-têtes contenant les IP émetteur/destinataire

**Équipements :** Routeurs, Protocoles IPv4 IPv6

### Couche 4 : Transport

**Fonction :** S'assure que les paquets arrivent dans l'ordre d'un nœud à un autre

**PDU :** Segments (TCP) ou Datagrammes (UDP)

**Encapsulation :** Ajoute des en-têtes contenant les numéros de ports TCP/UDP émetteur/destinataire

**Équipements :** Pare-feux, Protocoles TCP (données intactes) ou UDP (ne vérifie pas l'intégrité, pour le streaming, etc.)

### Couche 5 : Session

**Fonction :** Gère l'ouverture, maintenance et fermeture des sessions entre applications

**PDU :** Transactions "Données"

**Encapsulation :** Ajoute les infos de contrôle de session

**Équipements :** passerelles réseaux, protocoles SAP et netBIOS

### Couche 6 : Présentation

**Fonction :** Syntaxe des données, encodage des caractères, compression, chiffrement et déchiffrement des données

**PDU :** Données

**Encapsulation :** Formate les données si nécessaire

**Équipements :** Logiciels de traduction des données

### Couche 7 : Application

**Fonction :** Fourni les données à l'utilisateur final

**PDU :** Données

**Encapsulation :** Prépare les données pour la transmission

**Équipements :** les logiciels et applications

  

## Les câbles

### Fibre VS Cuivre

La fibre est plus cher que le cuivre mais est généralement plus rapide et peut transmettre sur de longues distances. Elle est aussi mieux immunisée faces aux interférences et perturbations.

Le cuivre est moins cher et est mieux normalisé au niveau des connecteurs.

### Câbles de raccordements

Ils servent à relier les équipements.

Soit entre

- un hôte et la prise murale RJ45 femelle

- un switch et le tableau de connexions dans une armoire de répartition

#### câblage horizontal

Relie les équipements avec prises RJ45 à l'armoire de répartition de l'étage.

#### câblage vertical

Relie les armoires de répartition de chaque étage.

### Les types de câbles à paire torsadée (Twisted Pair, TP)

- UTP : "unshielded", pas blindée

- FTP : "foiled", blindage **globale** avec aluminium

- STP : "shielded", blindage de **chaque paire individuellement** avec aluminium

- S/FTP : À la fois blindée globalement et individuellement

- SF/FTP : Triple blindage, deux blindages globaux + un blindage individuel

## Les adresses de niveau 2

Aussi appelées adresses MAC (Media Access Control).

Elles sont composées de 48 bits (6 octets).

On les représente en hexadécimale, et on les sépare avec des tirets, deux points ou points.

### Les deux parties

l'adresse MAC peut être coupée en deux parties de 24 bits chacune.

 - Partie OUI : (Organizationnally Unique Identifier) : 24 premiers, identifie le constructeur

 - Partie NIC : (Network Interface Controller) : identifie l'appareil

### Les types d'adresses

- Mono-diffusion : l'adresse MAC unique d'un appareil

- Diffusion (broadcast) : FF:FF:FF:FF:FF:FF, sert à communiquer sur un réseau local avec les autres appareils.

### Tables de commutation (FIB, forwarding information base)

Gérée par le commutateur (switch), pas besoin d'intervention humaine.

Elle indique quelle adresse MAC des trames reçues correspond à quel port.

![[Pasted image 20241203095837.png]]

### Les équipements de niveau 2

Les ponts (bridge) et commutateur (switch) sont les équipements qui travaillent à ce niveau.

Les routeurs arrêtent les diffusions (broadcast).

## Les adresses de niveau 3 (IPv4)

Composée de 32 bits (4 octets), représenté en décimal pointe (séparateur `.`).

Il y a deux adresses réservées :

- 0.0.0.0/8 : non attribuable

- 127.0.0.1/8 : loopback

Et des adresses IP privées (RFC 1918) pour les réseaux locaux et intranet :

- 10.0.0.0/8

- 172.16.0.0/12

- 192.168.0.0/16

Enfin, il y a aussi les adresses APIPA pour l'attribution automatique d'IP par le DHCP :

- 169.254.0.0/16

### Diffusions

- La diffusion dirigée : envoie à tous les hôtes d'un réseau spécifique via l'adresse de diffusion du réseau ciblé

- La diffusion limitée : envoie à tous les hôtes du réseau local

Les adresses de multicast : 224.0.0.0 à 239.255.255.255 envoient un paquet à un groupe d'hôtes spécifiques.

### La table ARP

Elle est constituée d'une IP et de l'adresse MAC associée.

Elle est générée automatiquement, sans intervention humaine.

![[Pasted image 20241203101849.png]]

## Routage

### La table de routage

La structure d’une table de routage contient des entrées nécessaires concernant **l’adresse réseau cible, les masques de sous-réseau, les passerelles (routeurs), les interfaces ainsi que les métriques** telles que le nombre de sauts ou l’effort de routage.

Les entrées peuvent être manuelles/statiques, et donc faites par l'administrateur (intervention humaine).

![[Pasted image 20241203102732.png]]

## Commandes Microsoft

- Afficher le résumé des configurations IP : `ipconfig`.

- Afficher l’intégralité des configurations IP : `ipconfig /all`.

- Afficher les tables ARP : `arp -a`.

- Réinitialiser les tables ARP : `arp -d`.

- Lister les interfaces traversées par un paquet IP : `tracert`.

- Tester la connectivité de niveau 3 : `ping`.