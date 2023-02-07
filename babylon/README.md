# Babylon contextualized for AIP deployment

## Summary

1. Babylon installation
2. Babylon configuration
3. Babylon script customization
4. Run Babylon Script
5. Troubleshooting

## 1. Babylon installation

### Requirement

- Operating System in [Debian 10, Debian in Wsl 2]
- docker (running)
- az cli :  install [azure cli](https://learn.microsoft.com/fr-fr/cli/azure/install-azure-cli) to authenticate anc access to azure resources.
- git cli
- python3

### Babylon installation

Install Babylon via pip steps

> Clone babylon repository

```bash
# Clone babylon repository
git clone https://github.com/Cosmo-Tech/Babylon.git
```

> Create Python 3 virtual environnement in Babylon directory

⚠️ Babylon development team highly recommend to install babylon in an python virtual environnement. Using virtual environnement allow you to install many instance of different version of babylon without any risk of conflict.

```bash
# Create Python 3 virtual environnement in Babylon directory
cd Babylon
python3 -m venv .venv
```

> Activate Python environnement

```bash
# Activate Python environnement
source .venv/bin/activate
```

> Install Babylon and his dependencies

```bash
# Install Babylon and his dependencies
pip install .
```

Full installation script

```bash
# Clone babylon repository
git clone https://github.com/Cosmo-Tech/Babylon.git
# Create Python 3 virtual environnement
cd Babylon
python3 -m venv .venv
# Active Python environnement
source .venv/bin/activate
# Install Babylon and his dependencies
pip install .
# Test babylon commad
cd ..
```

Once the babylon installation complete you can run `babylon` in your terminal to check installation.

You can add more features to your Babylon installation, visit [babylon documentation](https://cosmo-tech.github.io/Babylon/1.1.1/installation/)

## Babylon directory configuration

Babylon working directory is the root of the project repository (this repository).