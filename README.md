# The Study
A learning resource that I am building to share with my team members who would like to collaborate.
FILE NAME GUIDE
pb = playbook
example pb_host_info.yaml is a ansible playbook that returns information about your inventory devices in a file called host.ini

INVENTORY
you will need to create a host.ini file 
It should look something like this: 
[raspberry_pis]
	raspberry_pi_1 ansible_host=192.168.1.10
	raspberry_pi_2 ansible_host=192.168.1.11
	raspberry_pi_3 ansible_host=192.168.1.12

Replace 192.168.1.10, 192.168.1.11, and 192.168.1.12 with the actual IP addresses of your Raspberry Pis.
