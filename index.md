# DevLogBus Linux Package Repository

This static package repository is published from GitHub Pages and contains
DevLogBus Linux packages for Debian/Ubuntu, Fedora/RHEL/openSUSE style systems,
and Alpine Linux.

Repository base URL:

```text
https://dan-sherwin.github.io/devlogbus-linux-repo
```

## Debian / Ubuntu

```bash
curl -fsSL https://dan-sherwin.github.io/devlogbus-linux-repo/keys/devlogbus-archive-key.asc | sudo gpg --dearmor -o /usr/share/keyrings/devlogbus-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/devlogbus-archive-keyring.gpg] https://dan-sherwin.github.io/devlogbus-linux-repo/apt stable main" | sudo tee /etc/apt/sources.list.d/devlogbus.list
sudo apt update
sudo apt install devlogbus
```

## Fedora / RHEL / openSUSE

```bash
sudo curl -fsSL -o /etc/yum.repos.d/devlogbus.repo https://dan-sherwin.github.io/devlogbus-linux-repo/rpm/devlogbus.repo
sudo rpm --import https://dan-sherwin.github.io/devlogbus-linux-repo/keys/devlogbus-archive-key.asc
sudo dnf install devlogbus
```

Use `sudo zypper install devlogbus` on openSUSE.

## Alpine Linux

```sh
sudo wget -O /etc/apk/keys/devlogbus@dan-sherwin.rsa.pub https://dan-sherwin.github.io/devlogbus-linux-repo/keys/devlogbus@dan-sherwin.rsa.pub
echo "https://dan-sherwin.github.io/devlogbus-linux-repo/alpine/$(apk --print-arch)" | sudo tee -a /etc/apk/repositories
sudo apk update
sudo apk add devlogbus
```

## Signing Keys

- APT/RPM GPG fingerprint: `BE890A0D4072D25B97D7F84D2BDF255EF7EE0C9B`
- Alpine public key: `devlogbus@dan-sherwin.rsa.pub`

## Current Version

`devlogbus 1.3.1`
