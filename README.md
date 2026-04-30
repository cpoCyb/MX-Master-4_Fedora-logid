# 🖱️ MX Master (logid) Setup Guide

## ✅ Installation (Ubuntu / Debian)

```bash
sudo apt update
sudo apt install git cmake libevdev-dev libudev-dev libconfig++-dev
```

## ✅ Installer logiops (version Git)

```bash
git clone https://github.com/PixlOne/logiops.git
cd logiops
mkdir build
cd build
cmake ..
make
sudo make install
```

## ✅ Activer le service

```bash
sudo systemctl enable --now logid
```

Vérifier :
```bash
logid --version
```

---

## ✅ Configuration

Éditer le fichier :

```bash
sudo nano /etc/logid.cfg
```

Puis coller le contenu de `logid.cfg` fourni dans ce dépôt.

---

## ✅ Redémarrer le service

```bash
sudo systemctl restart logid
```

---

## 🎯 Résultat

- ✅ Bouton avant → Copier (Ctrl+C)
- ✅ Bouton arrière → Coller (Ctrl+V)
- ✅ Molette latérale → Volume
- ✅ Scroll fluide + SmartShift actif

---

## 🚀 Bonus

Tu peux aller plus loin :
- gestes bureau
- Alt+Tab
- actions par application
