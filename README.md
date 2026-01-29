# reset-password-linux
## Installation sur disque dur (`/dev/sdb1`)

---

## 🧩 Contexte

- Kali Linux est installé sur **un disque dur externe**
- La partition système est : **/dev/sdb1**
- Le mot de passe utilisateur et/ou root est **oublié**
- Le système ne démarre pas car l’accès est bloqué
- Un autre Linux fonctionnel est disponible (Live USB ou OS installé)

🎯 **Objectif :** réinitialiser le mot de passe **sans perdre de données**

---

## ⚠️ Prérequis

- Accès **root** ou `sudo`
- Le disque dur externe branché
- Le système de fichiers est **non chiffré (pas LUKS)**

---

## 🧭 Étape 1 — Identifier la partition Kali

Lister les disques et partitions :

```bash
lsblk

sdb
└─sdb1   ext4   kali-root

sudo mkdir -p /mnt/kali

sudo mount /dev/sdb1 /mnt/kali

ls /mnt/kali



sudo mount --bind /dev  /mnt/kali/dev
sudo mount --bind /proc /mnt/kali/proc
sudo mount --bind /sys  /mnt/kali/sys


sudo chroot /mnt/kali /bin/bash
```
