# Curso Ansible com Wordpress Alura


projeto completo depois de terminar o curso de ansible

necessario ter instalado o vagrant e o virtualbox no computador

no diretorio principal abra o terminal e execute o comando
```
 vagrant up
```

apos as maquinas inicializarem entre na maquina que esta instalado o ansible
```
vagrant ssh ansible
```

rode o ansible e ele ja ira instalar e consfigurar para voce
```
ansible-playbook -i /vagrant/configs/ansible/hosts /vagrant/configs/provisioning.yml
```

acesse atravez do navegador o ip: 192.168.1.24
