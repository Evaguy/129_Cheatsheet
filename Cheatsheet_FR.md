## Paramètres terminal :
Montrer l'IP du terminal :
```
show ip
```
Configuration IP terminal :
```
ip ip_machine masque_sr ip_router
```
Exemple :
```
ip 192.168.1.128 /24 192.168.1.254
```
Sauvegarder :
```
save
```
## Paramètres mdp SU
Aller dans le répertoire terminal :
```
configure terminal
``` 
OU
```
conf t
```
Mettre le MDP
```
enable password mdp
```
Quitter le répertoire terminal :
```
exit
```
OU la combinaison de touches :  
CTRL+Z
### Test pour mdp SU
quitter le mod SU :
```
disable
```
Rentrer dans le mod SU :
```
enable
```
Puis, entrer le mdp.
## Instructions pour save config
Pour "copier" la running config sur la start up config :
```
copy running-config startup-config
```
OU plus rapide mais plus risquer 
```
wr
```
## Montrer la config
Montrer la running config :
```
show running-config
```
Montrer la start up config :
```
sh start
```
## Paramètre interface
### Sur le routeur
Répertoire terminal :
```
conf t
```
Interface (ex. dans le cas ou l'interface est la Fast-Ethernet 0/0) :
```
int fast 0/0
```
^ Commande réduite :)
Set l'IP :
```
ip addr ip_machine masque_sr
```
Set le mode :
```
full-duplex
```
Paramètre pour que l'interface ne se désactive pas :
```
no shutdown
```
Quitter :
CTRL+Z
montrer la running-config. :
```
sh run
```
Sauvegarder la config. :
```
wr
```
### Sur la machine
Effectuer un ping sur l'interface :
```
ping ip_routeur
```
## Fixer un nom de domaine
Répertoire terminal :
```
conf t
```
Fixer le nom de domaine :
```
ip domain-name nom.de.domaine
```
Quitter le répertoire terminal :
```
exit
```
montrer la running-config. :
```
sh run
```
Sauvegarder la config. :
```
wr
```
## Configurer l'heure du routeur
Aller dans le répertoire terminal :
```
conf t
```
Configurer l'heure (dans le cas UTC+1):
```
clock timezone utc 1
```
Aller dans le root :
```
exit
```
montrer la running-config. :
```
sh run
```
Sauvegarder la config. :
```
wr
```
## Configurer la date du routeur
Pas besoin d'aller dans le répertoire terminal pour la manipulation.
Set la date :
```
clock set heure:minutes:secondes jour mois année
```
Les jours doivent être inscrit en NB !!!
Exemple :
```
clock set 12:30:00 26 feb 2025
```
Montrer la date du routeur :
```
sh clock
```
Sauvegarder la config. :
```
wr
```
## Changer le nom du périphérique
Aller dans le répertoire terminal :
```
conf t
```
Changer le nom :
```
hostname name
```
Quitter le répertoire terminal
```
exit
```
Sauvegarder la config. :
```
wr
```
## Paramétrage des routes statiques
Aller dans le répertoire terminal :
```
conf t
```
Paramétrage d'une route statique :
```
ip route réseau_de_destination masque de sous réseau passerelle
```
exemple :
```
ip route 10.0.100.4 255.255.255.252 10.0.100.2
```
Revenir a la racine :
CTRL+Z
Montrer la route statique :
```
sh ip rou
```
Sauvegarder la config. :
```
wr
```
## Paramétrage routes dynamique (RIP2)
test de com. :
```
ping adresse machine
```
configuration terminal :
```
conf t
```
mode RIP :
```
router rip
```
spécifier sa version :
```
version 2
```
version 1 pour du classfull, version 2 pour du classless !
puis spécifier les réseaux :
```
netowrk ip_réseau
```
exemple :
```
network 192.168.1.0
```
retourne racine :
CTRL+Z
Sauvegarder la config. :
```
wr
```
montrer les routes :
```
sh ip route
```
C --> entrée mis automatiquement 

R --> entrée que nous avons configuré

## Tests (RIP2)
pour voir la route sur un PC :
```
trace adresse_de_destination
```
exemple :
```
trace 10.0.0.128
```






