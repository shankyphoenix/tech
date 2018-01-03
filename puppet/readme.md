# Puppet Configuration (*with docker*)

## Run container

> sudo docker start puppetmaster

> sudo docker start puppetagent

## Create master server 
create a docker bash server
>sudo docker run --name puppetmaster -it devopsil/puppet bash 

set a host name for ex: master.demo.com
>vi /etc/sysconfig/network

set add host name for ex: 172.17.0.2 master.demo.com
>vi /etc/hosts

to check network connection
>ping agent.demo.com

install puppet server
>yum install -y puppet puppet-server facter

config master puppet add this link under "main" section "certname = master.demo.com"
>vi /etc/puppet/puppet.conf

start puppetmaster
>service puppetmaster start

checkstatus
>service puppetmaster status

list all agent asking for cert
>puppet cert list

to sign the agent certificate **Running "$puppet cert list" will display host name of the agent system.

> vi /etc/puppet/manifests/site.pp
> 
```
puppet cert sign <agent_hostname>
 file { "/var/tmp/testfile":
    ensure => "present",
    owner => "root",
    group => "root",
    mode => "664",
    content => "This a test file",
  }
```



## Create agent server 


Install server for puppet agent.

>sudo docker run --name puppetagent -it devopsil/puppet bash

set a host name for ex: agent.demo.com
>vi /etc/sysconfig/network

set add host name for ex: 172.17.0.2 agent.demo.com
>vi /etc/hosts

to check network connection
>ping master.demo.com

install puppet agent
>yum install -y puppet facter

config master puppet add this link under "main" section " server = master.demo.com"
>vi /etc/puppet/puppet.conf

generate a certificate and sent to master for sign and wait for 50 second.
>puppet agent --test --server=master.demo.com --waitforcert=50

manually fetch task to do .
>puppet agent --test

