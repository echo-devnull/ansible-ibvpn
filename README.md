ibvpn
=========

This roles installs openvpn and squid on a machine to which the role is applied.
  * Openvpn is setup to connect with the servers from ibvpn.com.
  * Squid is installed so you can point your browser to your VM and use the tunnel.

Requirements
------------

You will need to provide your own vm/host to which this role can be applied

Role Variables
--------------

### ibvpn_remotes
`ibvpn_remotes: ['us11.ibvpn.com', 'us15.ibvpn.com', 'us16.ibvpn.com', 'us17.ibvpn.com', 'us18.ibvpn.com']`
List of the ibvpn servers you wish to use. These are used by Openvpn to connect to. They are randomly chosen.

### ibvpnemail
`ibvpnemail: your.email.address@gmail.com`
This is the email address you signed up with.

### ibvpnpassword
`ibvpnpassword: verysecretpassword`
And this is the password (Not you sign in password, you get issues one by ibvpn, and you can collect it from their site)

### ibvpn_localnet
`ibvpn_localnet: 0.0.0.0/0`
This is the network that squid will allow connections from. You should limit it to only your network (Like 192.168.0.0/24)


Example Playbook
----------------

    - hosts: ibvpn
      roles:
         - { role: markmaas.ibvpn, ibvpnemail: 'your.email.address@gmail.com', ibvpnpassword: 'P4ssw0rd', tags: ['ibvpn'] }

License
-------

GPLv3

Author Information
------------------

Mark Maas
Freelance IT
mark@maas-martin.nl
