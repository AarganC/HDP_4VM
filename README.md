# HDP_4VM
Cluster HADOOP_Centos6

# Créer et installer, des machines virtuel avec Vagrant. Create and setup virtual machine with Vagrant 
//Construction du cluster. Build the cluster.

HDP_4VM: vagrant up 

# Configuration machine virtuel. Configuration virtual machine.

//Connexion SSH. Connection SSH.

HDP_4VM: vagrant ssh VMName

//Passer en utilisateur "root". Switch to "root" user.

[vagrant@VMName ~]$ sudo su -

//Afficher le nom d'hote de la machine virtuel. Display hostname of the virtual machine.

[root@VMName ~]$ hostname

//Affiche le fichier "hosts". Display the "hosts" files.

[root@VMName ~]$ vi /etc/hosts

//Installation des paquets avec la commande yum install. Package install with the yum install command.

[root@VMName ~]$ yum install ntp //Service de protocole d'heure réseau. Service of Network Time Protocol 
[root@VMName ~]$ yum install wget //Service de téléchargement. Service of downloading.

//Configuration et lancement du service ntp. Management and launching of the service ntp.

[root@VMName ~]$ chkconfig ntpd on //Configure l'état de la machine et synchronise le cluster.  
                                   //Configure the state of the machine and synchronizes the cluster.
[root@VMName ~]$ service ntpd start //Lancement du service ntpd. Launch of the service ntpd.

# Sécuriser les connections ssh. Secure ssh connections.
//Génère une clé d'authentification pour sécuriser les connexions ssh. Generates an authentication key to secure ssh connections.

[root@VMName ~]$ ssh-keygen

//Changement de dossier. Change of folders.

[root@VMName ~]$ cd .ssh

//Copie du contenue de id_rsa.pub dans authorized_keys. Copy the contents od id_rsa.pub in authorized_keys.

[root@VMName .ssh]cat id_rsa.pub >> authorized_keys

# Ambari

//Télécharge un paquet sur http://public-repo-1.hortonworks.com/ambari/centos6/2.x/updates/2.2.1.0/ambari.repo.
//Download a package on http://public-repo-1.hortonworks.com/ambari/centos6/2.x/updates/2.2.1.0/ambari.repo.

[root@VMName ~]$ wget http://public-repo-1.hortonworks.com/ambari/centos6/2.x/updates/2.2.1.0/ambari.repo

//Copie le fichier téléchargé dans /etc/yum.repos.d. Copy the downloaded files to /etc/yum.repos.d.

[root@VMName ~]$ cp ambari.repo /etc/yum.repos.d 

//Verification de la configuration. Checks the configuration.

[root@VMName ~]$ yum repolist

# Ambari-server
//Installation des paquets Ambari-server. Install the packages Ambari-server.

[root@VMName ~]$ yum install ambari-server

//Paramétrage de l'ambari-serveur. Setup the ambari-server.

[root@VMName ~]$ ambari-server setup

//Lancement du serveur ambari. Launching the server ambari.

[root@VMName ~]$ ambari-server start

# Ambari-client
//Installation des paquets Ambari-agent. Install the packages Ambari-agent.

[root@VMName ~]$ yum install ambari-agent

//Lancement du serveur ambari. Launching the server ambari.

[root@VMName ~]$ ambari-agent start
