# Multicast Setup

This project includes ansible code designed to configure a cluster of nodes 
to permit exchange of multicasts packets.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

Currently, this code is designed for Centos 7 hosts but the roles can be adapted
for other platforms as necessary.

### Installing

$ git clone https://github.com/kbsheets/multicast_setup.git
$ vi inventories/hosts # Add hosts to inventory list
$ vi group_vars/all

Edit the 'interface' attribute of the 'mutlicast_route_settings' to match the 
NIC that will be used to manage multicast traffic in your network.

    multicast_route_settings:
         netmask: 240.0.0.0
         prefix: 224.0.0.0
         interface: eth1

$ ansible-playbook -i inventories/hosts [-u user] -k -K enable_multicast.yml

## Authors

* **Kitrick Sheets** - *Initial work* - [kbsheets](https://github.com/kbsheets)

## License

This project is licensed under the Apache License, Version 2.0 - see the [apache-license-2.0.md](apache-license-2.0.md) file for details

## Acknowledgments

* This code is an automation of techniques and approaches from various 
  net sourcs

  Including:
    * https://jupfaf.net/index.php?article10/multicast-between-virtual-machines-in-virtualbox
    * http://troglobit.com/howto/multicast/
    * https://www.ibm.com/support/knowledgecenter/en/SSQPD3_2.6.0/com.ibm.wllm.doc/runningiperfmulti.html

   Many thanks to the authors of these articles.
