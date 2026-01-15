# Proxmox

Ši repozitorija skirta Proxmox VE aplinkos pagrindams bei LXC konteinerių kūrimui.

## Turinys

- Proxmox VE apžvalga
- LXC konteinerio kūrimas
- Naudojamos komandos ir nustatymai
- Kūrimas per GUI ir per PVE terminalą

## Tikslas

Supažindinti su LXC konteinerių kūrimu naudojant Proxmox Virtual Environment (PVE) tiek grafinėje aplinkoje, tiek per komandų eilutę.

- pct create 100 local:vztmpl/debian-12-standard_12.0-1_amd64.tar.zst \
  --hostname lxc-test \
  --memory 512 \
  --swap 512 \
  --cores 1 \
  --net0 name=eth0,bridge=vmbr0,ip=dhcp \
  --rootfs local-lvm:8
pct start 100
pct enter 100
pct list
pct stop 100
pct destroy 100

