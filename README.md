# Docker-VPS Safety playbook set
This is a set of playbooks that can be used to make a VPS aimed at docker more safe than its default.

# Disclaimer
Feel free to fork, and alter.

# Usage:
- create your `ansible-inventory.yml` file from the .sample file
- `ansible-playbook -i ansible-inventory.yml ./playbooks/01-bootstrap-vpn-user.yml ` to secure your VPS SSH behind a VPN
- `sudo wg-quick up wg0` to connect to the VPN
- `ansible-playbook -i ansible-inventory.yml ./playbooks/02-set-user-docker.yml` to install docker and link the user to it 
- `ansible-playbook -i ansible-inventory.yml ./playbooks/03-https-via-ovh.yml` to install traefik and link it to docker network `web`