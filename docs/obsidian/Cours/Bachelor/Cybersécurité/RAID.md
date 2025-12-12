1988 

à l'origine :
Redundant Array of Inexpensive Disks


Maintenant :

Redundant Array of the Independant Disks




# RAID 0

aucune redondance donc an cas de perte c'est perdu 

4 disques en simultanés donc 

avantage : vitesse 

inconvénient : aucune récupération de données possible
![[Pasted image 20240920110358.png]]

# RAID 1

Mirroring

sur disque 1 on écrit ABCD
sur disque 2 on écrit ABCD

![[Pasted image 20240920110333.png]]


Le seul problème est le contrôleur de disque pour éviter les problemes on en met 1 par disque (duplexing) au lieu de 1 seul (mirroring)


## RAID 1E (Stripped mirroring)

![[Pasted image 20240920111126.png]]

# RAID5 

Le raid 5 est utilisé dans les petite entreprise et les pme 
Ajout de la parité 
![[Pasted image 20240920111237.png]]


ABCD + P 
0 1 0 1 + 0
1 1 1 0 + 1

Parité grâce au [[XOR]] 

parité séparé entre les 4 disques et un disque possible de secours en cas de problème de machine

on perds 1/4 de l'espace disque 

N-1 Disque 
# RAID 5EE


![[Pasted image 20240920112533.png]]


Plus rapide que le RAID 5 c'est déjà pas mal

# RAID 6 


![[Pasted image 20240920112753.png]]

N -2 Disque
on agit avec une double parité  P et Q basée sur des maths incompréhensible

# RAID 1 0 

![[Pasted image 20240920113116.png]]

RAID 0 PUIS RAID 1


# RAID 50 



![[Pasted image 20240920113209.png]]

RAID 50 on peut perdre 2 disques mais seulement 1 par grappe 