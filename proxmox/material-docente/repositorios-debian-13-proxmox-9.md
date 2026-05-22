# Configuración de repositorios en Debian 13 y Proxmox 9

Esta guía muestra cómo organizar los repositorios en formato moderno para **Debian 13 (Trixie)** y **Proxmox VE 9**.

---

## 1. Modernizar las fuentes APT
Ejecutar el siguiente comando para modernizar las fuentes de APT:
```bash
apt modernize-sources
```

## 2. Repositorio Debian 13
Repositorio principal de Debian 13:
```bash
Types: deb deb-src
URIs: http://deb.debian.org/debian/
Suites: trixie trixie-updates
Components: main non-free-firmware
Signed-By: /usr/share/keyrings/debian-archive-keyring.gpg
```
Repositorio de seguridad de Debian 13:
```bash
Types: deb deb-src
URIs: http://security.debian.org/debian-security/
Suites: trixie-security
Components: main non-free-firmware
Signed-By: /usr/share/keyrings/debian-archive-keyring.gpg
```

## 3. Repositorio Proxmox 9
Repositorio de Proxmox VE 9 sin suscripción:
```bash
Types: deb
URIs: http://download.proxmox.com/debian/pve
Suites: trixie
Components: pve-no-subscription
Signed-By: /usr/share/keyrings/proxmox-archive-keyring.gpg
```

## 4. Actualizar la lista de paquetes
Después de configurar los repositorios, ejecutar:
```bash
apt update
```

## 5. Verificar los repositorios configurados
Puedes revisar los archivos de repositorios con:
```bash
ls /etc/apt/sources.list.d/
```
También puedes verificar el contenido con:
```bash
cat /etc/apt/sources.list.d/*.sources
```







