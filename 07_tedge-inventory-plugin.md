# About

In this step, we're installing the [tedge-inventory-plugin](https://github.com/thin-edge/tedge-inventory-plugin). This is a plugin to support publishing inventory data using a simple script based interface. 

# Instructions

The plugin can be installed easily via:

```sh
# Setup community repo (in case this is not already done in previous steps)
curl -1sLf \
  'https://dl.cloudsmith.io/public/thinedge/community/setup.deb.sh' \
  | sudo -E bash

# Install the package
sudo apt-get install tedge-inventory-plugin=0.5.0
```

With this, the following will be installed: 

* A set of (default) scripts are put in `/usr/share/tedge-inventory/scripts.d/` 

* A systemd service (including timer) is running and will execute each script in above directory

That is particularly useful as a User/Developer can just put shell scripts in this directory and the service will parse the info from stdout and automatically set them as properties on the Cloud twin. 

Let's assume a script that echo's key=value data to stdout.  

```
#!/bin/sh

printf 'mymetric="%s"\n' "some string value"
echo "another_value=1"
echo "nested={\"values\":\"ok\"}"
```

Once this script is put in `/usr/share/tedge-inventory/scripts.d/` it will be executed regulary by thin-edge, and thin-edge will automatically update the properties `mymetric`, `another_value` and `nested` on your cloud twin.

**Note**: This is a useful plugin to set Cloud Twin properties. Of course, that is not the only option. The other options are e.g. to put your properties in the `inventory.json` file on your device (good for static properties) or to update your twin properties by sending data to the MQTT broker (good for dynamically changing properties). 
