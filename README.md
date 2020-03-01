Created to configure the resolv.conf with required name servers and make it immutable to any furtherchanges

Disable the resolv.conf managment by NetworkManager

create the resolv.cof from the jinja template and backup existing resolv.conf

Set resolv.conf to immutable state by using the +i attribute

env01 sets nameservers 8.8.8.8 and 8.8.4.4

env02 sets nameservers 8.8.4.4 and 8.8.8.8

tgroup is set to evaulate env01 and env02 group_names against roles env01 and env02 respectively by using when condition

usage

Try using below 
ansible-playbook -i invent.yml myplaybook2.yaml -e tgroup=env01


Role menv combines the functions of roles env01 and env02 into one role menv and the evaultaion is done on basis of the variable tgroup in playbook and that gets passed to role menv to evaluate logic within role 

use following to check

ansible-playbook -i invent.yml myplaybook3.yaml -e tgroup=env01


