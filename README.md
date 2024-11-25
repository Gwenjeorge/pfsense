Installer PfSense sur une VM, avec 2 adaptateurs WAN (en bridge) et LAN (en réseau internet).  
Lancer une VM Windows Server (admin) et une VM Windows 10 (client) toute deux sur le même adaptateur LAN.  
L'interface LAN du firewall : 192.168.1.1/24  
IP du client : 192.168.1.10/24  
IP de l'admin : 192.168.1.20/24   
Une fois le firewall installé, vérifié que l'interface en bridge communique avec internet.
Utiliser comme ci-après l'outil de diagnostic ping intégré.  

![image](/Pfsense/Ping.png)  

Etablir ensuite une règle dans Firewall -> Rules pour bloquer l'accès internet au client.  
Pour ce faire, indiquer comme source dans la partie LAN l'adresse IP du client.  
Il est aussi possible de créer un alias pour utiliser l'adresse MAC du client.

![image](/pfsense/Rules.png)  

Faites un ping vers internet puis appliquer la règle. Le second ping ne marche pas.  

![image](/pfsense/pingClient.png)  


Tester sur le poste admin si internet est toujours accessible, ce qui doit être le cas.  

![image](/pfsense/pingAdmin.png)  
