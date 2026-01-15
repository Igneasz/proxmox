# Proxmox

Ši repozitorija skirta darbui su Proxmox VE ir LXC konteineriais. 
Čia pateikiamas paprastas pavyzdys, kaip buvo kuriamas LXC konteineris laboratorinio darbo metu.

Proxmox VE yra virtualizacijos platforma, leidžianti kurti virtualias mašinas ir konteinerius.

---

### LXC konteinerio kūrimas

Konteineris buvo kuriamas naudojant Proxmox WEB sąsają ir PVE terminalą. 
Žemiau pateiktos pagrindinės komandos, kurios buvo naudojamos kuriant ir valdant LXC konteinerį.

```bash
pct create 100 local:vztmpl/debian-12-standard_12.0-1_amd64.tar.zst \
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
