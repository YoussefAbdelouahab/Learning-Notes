#Proxmox
## Remove 'Local-lvm'
[link](https://linuxintosh.wordpress.com/2020/08/23/proxmox-suppression-de-la-partition-local-lvm/comment-page-1/)

To remove local-lvm, do the following commands 
- lvremove /dev/pve/data
- lvresize -l +100%FREE /dev/pve/root
- resize2fs /dev/mapper/pve-root
- Delete manually local-lvm disk in the graphic interface
## Script installation 
[link](https://tteck.github.io/Proxmox/#proxmox-ve-post-install)
1. Proxmox VE Post Install : ``bash -c "$(wget -qLO -https://github.com/tteck/Proxmox/raw/main/misc/post-pve-install.sh)"``
2. Proxmox VE Kernel clean : ``bash -c "$(wget -qLO - https://github.com/tteck/Proxmox/raw/main/misc/kernel-clean.sh)"``
3. Proxmox VE Netdata : ``bash -c "$(wget -qLO - https://github.com/tteck/Proxmox/raw/main/misc/netdata.sh)"``
4. HJS Solutions : ``wget https://cds1.hjssolutions.uk/proxmoxtemplates/script/``
	1. ``chmod +x hjssolsetup.sh``
	2. ``./hjssolsetup.sh`` -> to setup & download virtual machines

## Passthrough PCI / GPU
Follow the [link](https://hjssolutions.uk/passthrough/#0-configuring-the-system-bios)
