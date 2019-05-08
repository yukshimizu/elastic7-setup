# elastic7-setup
Setup minimum Elasticsearch7.x and Kibana environment with vagrant and ansible.

## Pre-Requisites
- Vagrant 2.2.2 or later
- Ansible 2.7.5 or later
- Python 2.7

## Initial setup
This process setups 3 x Elasticsearch nodes and a Kibana node. If you want to change IP addresses, modify them in Vagrantfile and ek6.yml.

1. vagrant up
  - git clone
  - cd elastic7-setup
  - vagant up


2. After all the VMs have booted up, go to Kibana.
  - http://ip-address:5601/

## Enable security features in Elasticsearch
If you want to try all of the platinum features, you can start a 30-day trial.

1. Enable 30-day trial at Kibana
2. Configure security features
  - cd elastic7-setup
  - ansible-playbook ek7-sec.yml
3. Set built-in users' password
  - /usr/share/elasticsearch/bin/elasticsearch-setup-passwords interactive
  - NOTE: You need to align the password with elastic's one in ek7-sec.yml.

## Shutdown the environment
- cd elastic7-setup
- vagrant halt

## Destroy the environment
- cd elastic7-setup
- vagrant destroy
