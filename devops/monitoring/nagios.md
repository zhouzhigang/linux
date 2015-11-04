# Nagios

## Install

### Prerequisites

Apache, PHP, GCC compiler, GD development libraries

    $ yum install httpd php
    $ yum install gcc glibc glibc-common
    $ yum install gd gd-devel

### Create user and group for nagios

Create a new nagios user account and give it a password.

    # /usr/sbin/useradd -m nagios
    # passwd nagios

Create a new nagcmd group for allowing external commands to be submitted through the web interface. Add both the nagios user and the apache user to the group.

    # /usr/sbin/groupadd nagcmd
    # /usr/sbin/usermod -a -G nagcmd nagios
    # /usr/sbin/usermod -a -G nagcmd apache

### Download Nagios and plugin

    # wget http://prdownloads.sourceforge.net/sourceforge/nagios/nagios-4.0.8.tar.gz
    # wget http://www.nagios-plugins.org/download/nagios-plugins-2.0.3.tar.gz

### Compile and Install Nagios

Extract the Nagios source code tarball.

    # tar xzf nagios-4.0.8.tar.gz
    # cd nagios-4.0.8

Run the Nagios configure script, passing the name of the group you created earlier like so:

    # ./configure --with-command-group=nagcmd

Compile the Nagios source code.
    
    # make all

Install binaries, init script, sample config files and set permissions on the external command directory.

    # make install
    # make install-init
    # make install-config
    # make install-commandmode

### Customize Configuration

Edit the /usr/local/nagios/etc/objects/contacts.cfg config file with your favorite editor and change the email address associated with the nagiosadmin contact definition to the address you'd like to use for receiving alerts.

    # vim /usr/local/nagios/etc/objects/contacts.cfg

### Configure the Web Interface

Install the Nagios web config file in the Apache conf.d directory.

    # make install-webconf

Create a nagiosadmin account for logging into the Nagios web interface. Remember the password you assign to this account - you'll need it later.

    # htpasswd -c /usr/local/nagios/etc/htpasswd.users nagiosadmin

Restart Apache to make the new settings take effect.

    # service httpd restart

### Compile and Install the Nagios Plugins

Extract the Nagios plugins source code tarball.

    # tar xzf nagios-plugins-2.0.3.tar.gz
    # cd nagios-plugins-2.0.3

Compile and install the plugins.

    # ./configure --with-nagios-user=nagios --with-nagios-group=nagios
    # make
    # make install

### Start Nagios

Add Nagios to the list of system services and have it automatically start when the system boots.

    # chkconfig --add nagios
    # chkconfig nagios on

Verify the sample Nagios configuration files.

    # /usr/local/nagios/bin/nagios -v /usr/local/nagios/etc/nagios.cfg

If there are no errors, start Nagios.

    # service nagios start

### Login to the Web Interface

http://localhost/nagios/

## Configuration

Default position: `/usr/local/nagios/etc`

|File|Description|
+----+-----------+
|cgi.cfg|CGI|
|nagios.cfg|Main configuration file|
|resources.cfg|Resource file|
|objects|Directory|
|objects/commands.cfg||


## Reference
* [Nagios Quick Start](https://assets.nagios.com/downloads/nagioscore/docs/nagioscore/4/en/quickstart.html)
* [Main Configuration File Options](https://assets.nagios.com/downloads/nagioscore/docs/nagioscore/4/en/configmain.html)
