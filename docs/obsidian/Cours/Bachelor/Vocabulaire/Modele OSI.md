
Le **modèle OSI** (*Open Systems Interconnection*) est un cadre conceptuel utilisé pour comprendre et standardiser la communication entre différents systèmes informatiques. Il est composé de **7 couches**, chacune ayant une fonction spécifique.

---

## 🖼️ Vue d'ensemble des couches

1. **Couche 7 : Application**  
   Interagit avec l'utilisateur et fournit des services réseau aux applications.
   - Exemples : HTTP, FTP, SMTP.

2. **Couche 6 : Présentation**  
   Traduit les données pour qu'elles soient compréhensibles par les applications.
   - Fonctionnalités : cryptage, compression.
   - Exemples : SSL/TLS, ASCII.

3. **Couche 5 : Session**  
   Gère les connexions entre applications (établissement, maintien, terminaison des sessions).
   - Exemples : RPC, NetBIOS.

4. **Couche 4 : Transport**  
   Assure le transfert fiable des données entre les hôtes.  
   - Protocoles : TCP (fiable), UDP (rapide).
   - Concepts clés : segmentation, contrôle de flux.

5. **Couche 3 : Réseau**  
   Détermine le chemin pour acheminer les données (routage).  
   - Protocoles : IP, ICMP.
   - Exemples : routeurs.

6. **Couche 2 : Liaison de données**  
   Gère l'accès au support physique et la détection/correction d'erreurs.  
   - Protocoles : Ethernet, Wi-Fi.
   - Exemples : switchs, ponts (*bridges*).

7. **Couche 1 : Physique**  
   Transmission des bits sous forme de signaux électriques, optiques ou radio.  
   - Exemples : câbles, hubs, fibres optiques.

---

## 🕸️ Pourquoi utiliser le modèle OSI ?

- **Norme universelle** : facilite la compatibilité entre différents fournisseurs.  
- **Diagnostic des problèmes** : simplifie l'identification des erreurs en analysant une couche spécifique.  
- **Modularité** : permet d'améliorer ou de remplacer une couche sans affecter les autres.  

---

## 📚 Comparaison avec le modèle TCP/IP

| Fonctionnalité    | Modèle OSI             | Modèle TCP/IP          |
|--------------------|------------------------|-------------------------|
| Couches           | 7                      | 4 (Application, Transport, Internet, Réseau d'accès) |
| Utilisation       | Théorique              | Pratique, largement utilisé |
| Protocoles clés    | Très général           | TCP, IP, HTTP, etc.    |

---

## 🔗 Ressources utiles

- [RFC 1122 - Standards Internet](https://www.rfc-editor.org/info/rfc1122)
- [Explications sur le modèle OSI (Wikipedia)](https://fr.wikipedia.org/wiki/Mod%C3%A8le_OSI)

---
