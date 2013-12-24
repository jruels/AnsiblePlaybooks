## Magento+Nginx+PHP-FPM Deployment

- Requires Ansible 1.2 or newer
- Expects CentOS/RHEL 6.x hosts

These playbooks deploy a simple all-in-one configuration of the popular
Magento e-commerce platform, frontend by the Nginx web server and the
PHP-FPM process manager. To use, edit the "hosts" inventory file to include the
names of the servers you want to deploy, and set the database password in `./group_vars/all`

Then run the playbook, like this:

	ansible-playbook -i hosts site.yml

The playbooks will configure MySQL, Magento, Nginx, and PHP-FPM. When the run
is complete, you can hit access server to begin the Magento configuration. 

### Notes

- This set of playbooks was adapted for magento from [ansible/ansible-examples/wordpress-nginx](https://github.com/ansible/ansible-examples/tree/master/wordpress-nginx)
