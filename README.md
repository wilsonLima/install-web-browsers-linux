install-web-browsers-linux
=========

Role do Ansible com passos para a instalação de Web Browsers em Desktop Linux.

Distribuições Suportadas pela Role
------------

- Fedora 30 ou superior
- Linux Mint LMDE 3 ou superior
- Linux Mint 19.2 ou superior
- openSUSE Leap 42 ou superior
- openSUSE Tumbleweed
- Ubuntu 18.04 ou superior


Tags da Role 
--------------

- main: Tag a ser utilizada em conjunto com outras tags, se alguma tag for especificada no comando.
  
- repo: Inclui todos os repositórios da role no Sistema.

- web: Instala todos os browsers contidos na role.
- chrome: Instala o browser Google Chrome.
- opera: Instala o browser Opera.
- vivaldi: Instala o browser Vivaldi.


Dependências da Role 
--------------

openSUSE Leap e Tumbleweed

  - No caso do vivaldi, ter o repositório de extras Packman configurado: https://en.opensuse.org/Additional_package_repositories


Linux Mint e Ubuntu:

- openssh-server. Ex.: sudo apt install openssh-server


Exemplo de Inventario
----------------

Exemplo de arquivo de hosts: pasta_invetario/hosts

    [NOME]
    IP ansible_connection=ssh ansible_ssh_user=USUARIO ansible_ssh_pass=SENHA_URUARIO ansible_become_pass=SENHA_ROOT


Especificar interpretador python 3: pasta_invetario/group_vars/all

    ansible_python_interpreter: "/usr/bin/python3"


Exemplo de Playbook
----------------

Exemplo de uso da Role, com as configurações padrão:

    - hosts: desktop
      roles:
         - setup-desktop-linux


Exemplo de Comandos
----------------

Comando para executar todas as tasks:

    ansible-playbook -i <caminho_inventario> <caminho_playbook>

Comando para executar a tag "web" (em caso de uso de tags, a tag "main" é obrigatória):

    ansible-playbook -i <caminho_inventario> <caminho_playbook> --tags "main, web"


License
-------

MIT License