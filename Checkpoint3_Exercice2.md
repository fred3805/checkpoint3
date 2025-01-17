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



