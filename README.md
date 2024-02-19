# sou-lab-cni
DevOps – Vagrant, Ansible, Prometheus, Grafana e HaProxy

# Version v1.0
 - Creazione di un repository in GitHub denominato "sou-lab-cni".
 - Creazione di un progetto Vagrant multinodo (2 nodi: soufe1 e soube2) con comunicazone su interfacce network 
   locali (scegliere una subnet a piacere in 192.168.0.0/16).
 - Scegliere la distribuzione tra Centos, Almalinux, RockyLinux e Oracle Linux.

 # Notes per version v1.0
 - Reference links : 
    - https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_roles.html
    - https://mariadb.com/kb/en/creating-a-vagrantfile/ 
    - https://developer.hashicorp.com/vagrant/docs/vagrantfile 

# Version v1.1 
 - Creazione di un ruolo Ansible denominato sou_podman. Nei punti successivi sono espresse le azione che deve compiere l'automatismo.

# Notes per version v1.1
 - Creo il ruolo: 
    - ansible-galaxy init sou_podman
 - Reference links : 
    - https://docs.ansible.c2om/ansible/latest/playbook_guide/playbooks_reuse_roles.html 
    - https://spacelift.io/blog/ansible-roles 
    - https://www.devopsschool.com/tutorial/ansible/ansible-roles-explained-with-examples.html

# Version v1.2
 - Installare podman su soufe1 e soube2. 

# Notes per version v1.2
 - Reference links: 
   - https://docs.ansible.com/ansible/latest/collections/containers/podman/podman_container_module.html#examples 

# Version v1.3
 - Installare HaProxy su soufe1 tramite podman e utilizzare un template Ansible per haproxy.cfg.
 - Installare Prometheus e Grafana tramite podman su soube2. 
 - Utilizzare volumi ad-hoc per dati e file di configurazione. 
 - I file di configurazione grafana.ini e prometheus.yml occorre che siano gestiti tramite template Ansible. 
 - Poter raggiungere Grafana e Prometheus via http o https (bonus per https con creazione certificati anche self-signed).
 - HaProxy deve quindi operare come Reverse proxy per Prometheus e Grafana.

# Notes per version v1.3 
 - Reference links: 
   - https://gist.github.com/bhameyie/07c1ee9aaa3e8a200c8c 
   - https://community.grafana.com/t/reverse-proxying-behind-haproxy-does-not-work/34103
   - https://github.com/grafana/grafana/blob/main/conf/sample.ini 
   - https://www.tutorialworks.com/podman-rootless-volumes/ 
   - https://grafana.com/tutorials/run-grafana-behind-a-proxy/ 
   - https://github.com/prometheus/prometheus/issues/4925 
   - https://docs.podman.io/en/latest/markdown/podman-volume-mount.1.html 
   - https://docs.podman.io/en/v4.4/markdown/options/volumes-from.html
   - https://www.haproxy.com/documentation/haproxy-configuration-tutorials/dns-resolution/
   - https://github.com/openfaas/faasd/blob/master/prometheus.yml  