# OpenVPN Panel
A web panel for controlling an OpenVPN server

## Setup

Add this direcory to your path variable either in `~/.bashrc` or using
```
export PATH=$PATH:/this/directory
```

## Installation
```
# Download OpenVPN Panel
git clone https://github.com/nathan-fiscaletti/openvpn-panel.git
cd openvpn-panel

# Modify Configuration
#    Set `host` and `port` values in config/server.ini
#    Set `client_storage` in config/server.ini
#        All client configurations will be stored here. This needs to be
#        the same location that is configured in WebConfig.php, and the
#        directory needs to be created before you start the OpenVPN Panel.
#    Set `client_storage` in config/WebConfig.php

# Install Dependencies
sudo apt-update
sudo apt install php composer -y
composer install

# Set up the OpenVPN Server
./bin/openvpn-install.sh

# Add the default user for the Panel
# (Use a secure password)
sudo openvpnpanel --adduser admin 'password'

# Start the Panel
sudo ./openvpnpanel --start
```

## Commands

### Start the panel
```
openvpnpanel --start
```

### Stop the panel
```
openvpnpanel --stop
```

### Get the status of the Panel
```
openvpnpanel --status
```

### Add Panel User
```
openvpnpanel --adduser [name] [password]
```

### Remove Panel User
```
openvpnpanel --deleteuser [name]
```

