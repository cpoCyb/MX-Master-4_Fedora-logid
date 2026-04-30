# 🖱️ MX Master 4 - Fedora (logid)

Configuration complète pour utiliser pleinement la Logitech **MX Master 4** sous **Fedora** avec **logiops (logid)**.

Ce dépôt fournit :
- ✅ Installation propre depuis les sources (version compatible MX Master 4)
- ✅ Activation automatique via systemd
- ✅ Configuration optimisée (`logid.cfg`)
- ✅ Gestes + raccourcis personnalisés

---

# ⚙️ Prérequis

- Fedora (testé sur versions récentes)
- Droits sudo
- Souris Logitech MX Master 4

---

# 🚀 Installation

## 1. Installer les dépendances

```bash
sudo dnf install git cmake gcc-c++ libevdev-devel systemd-devel
```

---

## 2. Installer logiops (version Git recommandée)

⚠️ Important : la MX Master 4 nécessite une version récente non disponible dans les dépôts Fedora.

```bash
git clone https://github.com/PixlOne/logiops.git
cd logiops
mkdir build && cd build
cmake ..
make
sudo make install
```

---

## 3. Activer le service

```bash
sudo systemctl enable --now logid
```

Vérifier qu’il tourne :

```bash
systemctl status logid
```

---

# 📁 Configuration

## 1. Copier le fichier de config

```bash
sudo cp logid.cfg /etc/logid.cfg
```

---

## 2. Redémarrer le service

```bash
sudo systemctl restart logid
```

---

# ✅ Vérification

Lancer :

```bash
sudo logid -v
```

Tu dois voir ta souris détectée (**MX Master 4**).

---

# 🎯 Fonctionnalités incluses

- ✅ SmartShift activé (molette auto libre/crantée)
- ✅ Scroll haute résolution
- ✅ Bouton pouce → gestes personnalisés
- ✅ Contrôle multimédia (volume, play/pause, pistes)
- ✅ Navigation navigateur (avant / arrière)
- ✅ Raccourcis clavier (copier, coller, switch apps)

---

# 🛠️ Personnalisation

Le fichier principal :

```bash
/etc/logid.cfg
```

Tu peux modifier :
- les boutons
- les gestes
- les raccourcis clavier
- la sensibilité

---

# ⚠️ Dépannage

## Le service ne démarre pas

```bash
sudo journalctl -u logid -f
```

---

## La souris n’est pas détectée

- Vérifie le nom exact dans `logid.cfg`
- Teste avec :

```bash
lsusb
```

---

## Problème après modification

```bash
sudo systemctl restart logid
```

---

# 💡 Notes

- logiops remplace Logitech Options (non disponible sous Linux)
- Certaines fonctionnalités avancées dépendent du reverse engineering
- Cette config est optimisée pour une utilisation quotidienne (dev + bureautique)

---

# 📜 Licence

Libre d’utilisation et modification.
