**Partie 1 : Particularité des Unix**  

Q.1.1.1
Créer l'utilisateur Lionel Lemarchand avec les même attribut de société que Kelly Rhameur.

![Capture d’écran 2025-01-17 095400](https://github.com/user-attachments/assets/96381fb7-4108-4454-9b65-7414d01a7cba)  

Q.1.1.2 

![Capture d’écran 2025-01-17 100052](https://github.com/user-attachments/assets/474b3f79-7893-466f-917e-4a64b75924a7)  

Q.1.1.3

![Capture d’écran 2025-01-17 100503](https://github.com/user-attachments/assets/acc6cdf2-9ce4-496c-b60f-fcef4212c1fa)  

Q.1.1.4 

**Partie 2 : Restriction utilisateurs**  

Q.1.2.1

![Capture d’écran 2025-01-17 103032](https://github.com/user-attachments/assets/9a859d26-03d7-4657-89b1-54a219438a17)  

Q.1.2.2   

![Capture d’écran 2025-01-17 103355](https://github.com/user-attachments/assets/677a145c-f67a-4fa4-bb4b-125fc3f9d12e)  

**Partie 3 : Lecteurs réseaux**

Q.1.3.1   

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









