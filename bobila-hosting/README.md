# Bobila hosting ansible playbook

This playbook configures a LAMP server plus FTP, Monitoring based in New Relic and iptables filters for the aforementioned services in a CentOS 6.5 host.

This playbook can be run multiple times and if no manual changes have been done in the host, everything should keep working and configured as expected.

#### Ready:

 * Apache2 web server
 * MySQL database server
 * PHP 
 * vsftpd
 * New Relic system and PHP daemons
 

#### Steady:

Variables that can be or <code>must be</code> specified when running the playbook:

```yaml
# Enable or disable New Relic monitoring installation
- monitoring_enabled
    Default: TRUE
    
# Specifies server timezone
- default_timezone 
    Default: Europe/Madrid

# Specifies MySQL root password
- mysql_root_password
	Default: dummypassw0rd

# Specifies New Relic API key
- new_relic_key
	Default: 5acc8a8e204459d2baa3aa53741fab0a8621caef [invalid key]
```

#### Go:

To run the playbook you just need to edit <code>hosts</code> file and specify the IP address or DNS name of the server where want to install described playbook.

Run sample:

```bash
ansible-playbook -i hosts --extra-vars "mysql_root_password='myR3allY5st0nGP4ss' default_timezone='US/Central' new_relic_key='5acc8a8e204459d2baa3aa53741fab0a8621cxxx'
```

That's all!

You can have a look now to [bobila site setup] (http://github.com/danfaizer/ansible-playbooks/bobila-site) which setup a user account in the hosting server.
