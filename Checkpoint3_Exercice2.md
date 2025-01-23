**Exercice 2 : Manipulations pratiques sur VM Linux**  

**Partie 1 : Gestion des utilisateurs** 

Q.2.1.1  

![Capture d’écran 2025-01-17 110810](https://github.com/user-attachments/assets/62302abb-1dbe-4bdf-b9dc-7d65580ea7b1)  

Q.2.1.2 

Je preconise de redemarrer le system, de changer l'addresse ip  et le nom de la machine pour l'attribuer à l'utilisateur au demarrage  

**Partie 2 : Configuration de SSH**  

Q.2.2.1  

Pour le compte root,
nano /etc/ssh/sshd.config
ensuite aller sur "PermitRootLogin yes" et mettre no ou commenter la ligne
Valider les modifications et redemarrer le system avec la commande "service ssh restart"

Q.2.2.2  

Pour le compte utilisateur,
nano /etc/ssh/sshd.config
ensuite aller sur "PermitRootLogin prohibit-passorw" decommenter la  ligne et remplacer "prohibit-passorw" pas yes et decommenter aussi la ligne "Port 22"
Valider les modifications et redemarrer le system avec la commande "service ssh restart"  

Q.2.2.3   

Pour désactiver l'authentification par mot de passe, il se rendre dans "nano /etc/ssh/sshd.config" et decommenter la ligne "PubkeyAuthentication yes "  

**Partie 3 : Analyse du stockage**  

Q.2.3.1  

![Q 2 3 1](https://github.com/user-attachments/assets/5a701525-546b-4dcc-b025-44791b48f7d3)  

Q.2.3.2  

![Q2 3 2](https://github.com/user-attachments/assets/8c029ae5-cf37-417c-ae68-e5d7ae9d76c7)  

Q.2.3.3  

Création d'une partition sur le disque de 8 Go  
fdisk /dev/sdb  

Réparer le RAID  
mdadm --add /dev/md0 /dev/sdb1  

Q.2.3.4  

lvcreate --name LVMBackup --size 2G cp3-vg  
mkfs.ext4 /dev/cp3-vg/LVMBackup  
mount /dev/cp3-vg/LVMBackup /var/lib/bareos/storage/  
puis dans /etc/fstab/ ajouter la ligne  
/dev/cp3-vg/LVMBackup /var/lib/bareos/storage ext4 defaults  

Q.2.3.5  

Réponse en tapant la commande  
vgs  

**Partie 4 : Sauvegardes**  

Q.2.4.1 

bareos-dir (Director) : Coordonne les sauvegardes, récupérations et tâches de gestion.  
bareos-sd (Storage Daemon) : Gère le stockage et le transfert des données vers les médias. bareos-fd  
 (File Daemon) : Installe sur les machines à sauvegarder pour transmettre les données au bareos-sd.  

 **Partie 5 : Filtrage et analyse réseau**  

 Q.2.5.1  

 nft list ruleset  

 Q.2.5.2  

 ct state established, related accept : les connexions déjà établies.  
 iifname lo accept : trafic de bouclage.  
 tcp dport ssh accept : ssh. ip protocol icmp accept : ping (icmp). ip6 nexthdr icmpv6 accept : ping6 (icmpv6).  

 Q.2.5.3  

 ct state invalid drop : paquets ne pouvant pas être identifiés et tout le reste  

Q.2.5.4  

nft add rule inet inet_filter_table in_chain tcp dport { 9101-9103 } ct state new accept  

**Partie 6 : Analyse de logs**  

Q.2.6.1  

journalctl -t sshd | grep 'Failed'| tail  

 











