# vSphere-6.5-to-6.7U1-Upgrade

Upgrading VCSA with external PSC from 6.5 to embedded 6.7U1

## Environment

* ESXi 6.5 host `esx.dm.lab`
* DNS server `dns.dm.lab`
* 6.5 PSC `psc.dm.lab`
* 6.5 VCSA `vcsa.dm.lab`

## Upgrade PSC

* Mount 6.7 installer
* Copy upgrade templates local and edit
  * Temporary IP required
* Rename `psc` in vCenter to `psc-65`
* Change to directory `cd /Volumes/VMware\ VCSA/vcsa-cli-installer/mac/`
* Execute upgrade `./vcsa-deploy upgrade ~/Git/vSphere-6.5-to-6.7U1-Upgrade/PSC_on_VC.json --accept-eula`

Once the new PSC is deployed, monitor the status of the console of this VM. Once the new PSC assumes the IP and DNS name of the old PSC, we must reboot the VCSA to complete the installation. In the install cli, you will see the message `Proceed with certificate thumbprint check...` repeat. Once the VCSA has been restarted, the install cli will complete.

## Upgrade VCSA

