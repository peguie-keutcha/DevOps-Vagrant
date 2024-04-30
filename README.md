Projet1 : automatisation création de 3 machines virtuelles sous almalinux (srv-an,clx,cly) avec vagrant et VirtualBox 
J’ouvre le PowerShell ou cmd depuis mon Windows
-création du dossier des vm avec la commande mkdir vmalmainux
-je me déplace dans le dossier crée avec la commande cd vmalmainux
-une fois dans le dossier vmalmainux ,je fais un vagant  init almalinux/8 me permettant de télécharger un fichier vagrantfile en ruby,c’est dans ce fichier que j’irais déposer mon script d’automatisation pour mes 3 machines virtuelles avec les caractéristiques que j’auras choisi (voir fichier vagrantfile)
-une fois mon fichier ruby modifié je fais un vagrant up pour construire mes machines

Projet2 : connexion par ssh a un server par échange de clé depuis un client linux
Dans ce projet 2 ,nos 3 machines sont des os linux,le server sera SRV-AN et les machines clientes CLIx et CLIy
-Dans un premier temps je créais sur le server srv-an  2 utilisateurs nommé aisha et kelly,sur le client clix un utilisateur nommé  golden et sur le client cliy un utilisateur nommé pat
 
 


-création des clés ssh
Secure Shell ou SSH vous permet d’administrer à distance vos machines, via un terminal.
SSH permet de se connecter à l'aide d'un mot de passe ou d'une paire de clés SSH. La paire de clés SSH repose sur des procédés cryptographiques similaires aux certificats SSL, qui utilisent une partie privée (qui n'est jamais communiquée) et une partie publique (qui peut être transmise librement)
Avec l’utilisateur golden sur la clix la clé sera placé sur le chemin choisir par défaut pour stocké la clé (/home/golden/.ssh/id_rsa)
 
Avec l’utilisateur pat sur la cly ,je choisirais un chemin autre que celui par defaut pour complexifié la chose afin de présenté un autre mode de connexion ssh,pour l’utilisateur pat la clé seras logé dans le chemin suivant (/home/pat/ansible-key), qu’il faudrait préciser lors de la connexion
 
-copie de la clé publique a un utilisateur sur le server srv-an
L’utilisateur golden sur le client clix enverra sa clé a l’utilisateur distant aisha sur le server srv-an
L’utilisateur pat sur le client cliy enverra sa clé a l’utilisateur distant kelly sur le server srv-an, l’envoi de la clé de pat sera diffèrent car il faudrait préciser le chemin qui héberge la clé publique (ssh-copy-id -i /home/pat/ansible-key.pub kelly@192.168.1.28)
 
 
Les clés se trouverons dans un dossier avec le nom authorized_keys des utilisateurs choisi sur le server srv-an
-connexion des utilisateurs au server srv-an par échange de clé
aprés les échanges de clé les connexions des utilisateurs vers le server se feras maintenant automatiquement sans mot de passe grâce aux clés publiques et privées. Pour la connexion de pat on oublie pas de préciser son chemin de clé privé
 

(les screenshots dans le dossier servent à l'explication en image des commandes et résultats de commande)
et il y'a un fichier pdf qui explique les etapes du projet 
