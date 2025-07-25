# About

A repository to document the installation steps for my thin-edge.io setup. Setup consists of:

* thin-edge.io (including agent, mapper and mosquitto)

* Connecting to Cumulocity via its Certificate Authority and x.509 certificates

* Install/Configure the thin-edge plugin to manage OCI containers

* Install/Configure the thin-edge shell plugin that allows to send shell commands from remote

* Setup of "Remote Access" feature in Cumulocity to connect via SSH (without the need of VPN) to your Device 

* Installation of the tool Monit, to showcase how to access a Web-Server running in the Edge Network from Cumulocity

* Install/Configure the tedge-inventory-plugin. A plugin that gives a very easy option to maintain Cloud Twin Properties

Please find the details in the respective document.

# Notes and References

* A very good reference for a full-featured thin-edge installation is the [tedge-demo-container](https://github.com/thin-edge/tedge-demo-container). See [here](https://github.com/thin-edge/tedge-demo-container?tab=readme-ov-file#what-is-included) the list for what is included.

* Link for [thin-edge.io documentation](https://thin-edge.github.io/thin-edge.io/)

* Link to [Cumulocity](https://cumulocity.com/docs/)