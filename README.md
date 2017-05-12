# Ansible Debian Secure

## What is this repository for?

This project is an ansible playbook to automate the setup and security policy of your debian servers and VPS.
Roles include : 

- APT self update with unattended upgrades
- Proper setup of En_US locales
- Firewall (uwf) and iptables setup
- Creation of a user with RSA public key and ZSH shell in the sudoers group
- Disallow Password authentication and root SSH
- Limit incoming connections to the SSH port of your choice

After this setup, your debian server will be reasonably secured and accessible only through SSH on a custom port with the RSA key you will have defined.

There are of course ways to improve security further, but I consider this to be a reasonable level. Feel free to modify it as you see fit.

## How do I get set up?

This repository was made for Debian servers only and tested on debian 8 (jessie) from Mac and Linux.

1. Install ansible : http://docs.ansible.com/ansible/intro_installation.html#installation
2. Clone this repository
3. Change *group_vars/all/vars_default* to *group_vars/all/vars* and edit the file with your infos
4. Add your server(s) adress(es) in the hosts file
5. Launch the playbook from the folder with 
```ansible-playbook -i hosts provision.yml```
6. Once the job is finished you can access your server with : 
```ssh -p PORT your_username@your_server```

## Credits

- Raphaël Aparicio
- Mischa ter Smitten for the locales role


## Licence

Copyright (c) 2017 Raphaël Aparicio

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.