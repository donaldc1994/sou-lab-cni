# Creazione di 2 nodi
nodes = {
  'soufe1' => {
    :box => 'generic/oracle8',
    :ip => '192.168.56.10',
    :cpu => 1,
    :ram => 2048
  },
  'soube2' => {
    :box => 'generic/oracle8',
    :ip => '192.168.56.11',
    :cpu => 1,
    :ram => 2048
  }
}
# Definizione della configurazione per l'ambiente Vagrant utilizzando la versione 2 di vagrant.
Vagrant.configure("2") do |config|
    # Iterazione sui  nodi
    nodes.each do |name, node|
      # Per ogni nodo creo una nuova macchina virtuale (VM) con il nome dato.
      config.vm.define name do |servers|
        # Configuro le proprietà della VM.
        servers.vm.box = node[:box]  
        servers.vm.network "private_network", ip: node[:ip]
        servers.vm.hostname = name
        servers.vm.define name do |host|
        end
        
        # Creo una cartella sincronizzata tra l'host e la VM guest, mappando la directory corrente (".") sull'host su "/vagrant" sul guest.
        servers.vm.synced_folder ".", "/vagrant"
        
        # Configurazione del provider VirtualBox:
        servers.vm.provider :virtualbox do |vb|
          vb.gui = false
          vb.name = name
          vb.customize ["modifyvm", :id, "--memory", node[:ram]]
          vb.cpus = node[:cpu]
        end 
      end
    end
  end
  