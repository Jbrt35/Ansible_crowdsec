# Ansible_crowdsec
Script Ansible pour le déploiement automatisé de CrowdSec avec l'installation des collections HoneyGuard/cowrie et des collections WordPress. Le script prend également en compte la gestion des bouncers et l'envoi des remédiations vers une instance Elasticsearch

# Architecture 

```plaintext
crowdsec_ansible/
├── collections/
│   ├── cowrie.yaml
│   └── detection_code.yaml
├── scenarios/
│   ├── cowrie.yaml
│   └── detection_code.yaml
├── parsers/
│   └── cowrie.yaml
|   └── detection_code.yaml
├── acquis.yaml
├── http.yml
├── hosts.ini
└── install_crowdsec.yml
```

# Lancement du script Ansible
Clonage du dépot Github:
```
git clone https://github.com/Jbrt35/Ansible_crowdsec.git
cd Ansible_crowdsec
```
```
sudo ansible-playbook -i hosts.ini install_crowdsec.yml
```
La seule action manuelle de l'utilisateur est l'ajout du jeton API généré par le bouncer Wordpress au plugin CrowdSec de Wordpress. 
Dans le fichier http.yml, il peut être nécessaire de modifier l'IP de l'instance Elasticsearch par celle correspondante.
