# vSphere-6.5-to-6.7U1-Upgrade

Upgrading VCSA with external PSC from 6.5 to embedded 6.7U1

## Environment

* ESXi 6.5 host `esx.dm.lab`
* DNS server `dns.dm.lab`
* 6.5 PSC `psc.dm.lab`
* 6.5 VCSA `vcsa.dm.lab`

## Upgrade

* Mount 6.7 installer
* Copy upgrade templates local and edit
* Change to directory `cd /Volumes/VMware\ VCSA/vcsa-cli-installer/mac/`
* Execute upgrade `./vcsa-deploy upgrade ~/Git/ESXi-Installer-PXE-Boot/upgrade/PSC_on_VC.json --accept-eula`
