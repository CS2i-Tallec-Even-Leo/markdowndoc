
---
# 🧩 Trame Réseau et Sa Construction

Une **trame réseau** est l'unité de transmission de données au niveau de la **couche 2 (Liaison de données)** du modèle OSI. Elle encapsule les données à transmettre avec des informations de contrôle, permettant une communication fiable entre les dispositifs.

---

## 📦 Structure générale d'une trame

Une trame réseau se compose généralement des éléments suivants :

1. **En-tête (Header)**  
   Contient des informations de contrôle nécessaires pour l'acheminement et l'identification.
   
2. **Données (Payload)**  
   La charge utile, qui est la donnée réelle transportée par la trame.  
   
3. **Contrôle de fin (Trailer)**  
   Contient des mécanismes comme la détection d'erreurs.

---

## 🔍 Exemple : Trame Ethernet

Une trame Ethernet, utilisée couramment sur les réseaux locaux (LAN), est composée des champs suivants :

| Champ                      | Taille (bits) | Description                                                                |
| -------------------------- | ------------- | -------------------------------------------------------------------------- |
| Préambule                  | 56            | Synchronisation entre les dispositifs.                                     |
| Délimiteur de début        | 8             | Indique le début de la trame.                                              |
| Adresse MAC de destination | 48            | Adresse physique du destinataire.                                          |
| Adresse MAC source         | 48            | Adresse physique de l'émetteur.                                            |
| Type/EtherType             | 16            | Indique le type de protocole encapsulé (IPv4, IPv6, ARP, etc.).            |
| Données (Payload)          | Variable      | Données transportées, souvent encapsulées dans une couche supérieure (IP). |
| Contrôle CRC               | 32            | Vérification d'intégrité pour détecter les erreurs dans la trame.          |

---

## 🛠️ Construction d'une trame

Lors de la transmission d'une trame :

1. **Encapsulation**  
   Les données sont encapsulées à partir de la couche Application (modèle OSI) jusqu'à la couche Liaison. À chaque étape, des en-têtes spécifiques sont ajoutés.  

2. **Ajout des adresses**  
   - **Adresse MAC source** : identifie l'émetteur.  
   - **Adresse MAC destination** : identifie le destinataire.

3. **Ajout des mécanismes de contrôle**  
   - CRC pour détecter les erreurs.  
   - Délimiteurs pour signaler le début et la fin de la trame.  

4. **Transmission sur le média physique**  
   La trame est convertie en signaux électriques, optiques ou radio, et envoyée au destinataire.

---

## 🛡️ Détection et correction d'erreurs

- **Code CRC (Cyclic Redundancy Check)**  
   Utilisé pour vérifier l'intégrité de la trame lors de la réception.
   
- Si une erreur est détectée :  
   - La trame est rejetée.  
   - Le système peut demander une retransmission (dans le cas de protocoles fiables comme TCP).

---

## 🎓 Exemple pratique : Une trame capturée (Wireshark)

Voici un exemple de trame Ethernet capturée avec Wireshark :  

```
0000   ff ff ff ff ff ff 12 34 56 78 9a bc 08 00 45 00  
0010   00 3c 1c 46 40 00 40 06 b1 e6 c0 a8 01 68 c0 a8  
0020   01 01 00 50 00 18 b6 3c 00 00 00 00 70 02 fa f0  
0030   16 d0 00 00 02 04 05 b4 01 03 03 08 01 01 04 02
```

- **Adresse MAC Destination** : `ff ff ff ff ff ff` (Broadcast)  
- **Adresse MAC Source** : `12 34 56 78 9a bc`  
- **Type** : `08 00` (IPv4)  
- **Payload** : Données IP encapsulées.

---

## 🌐 Ressources supplémentaires

- [Wireshark : Analyse des trames](https://www.wireshark.org/)  
- [RFC 894 : Ethernet Frame](https://tools.ietf.org/html/rfc894)  

--- 