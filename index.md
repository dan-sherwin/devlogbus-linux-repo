# DevLogBus Linux Package Repository

This static package repository is published from GitHub Pages and contains
DevLogBus Linux packages for Debian/Ubuntu, Fedora/RHEL/openSUSE style systems,
and Alpine Linux.

Repository base URL:

```text
https://dan-sherwin.github.io/devlogbus-linux-repo
```

The default install commands favor fast local developer setup. Signed metadata
and keys are published for users who want the higher-assurance path, but
verification is a choice. If you skip it, you own that tradeoff.

DevLogBus provides the tools you need to maintain your own security, but it does
not force you to use them. Use the checksums, signing keys, and verification
instructions as you see fit, because I am not your mother and it is not my job
to make sure you wear a damn helmet. That choice belongs to you.

In short, piss on the electric fence if you want. Just don't act surprised when
physics files a bug report on your ass.

## Debian / Ubuntu

```bash
echo "deb [trusted=yes] https://dan-sherwin.github.io/devlogbus-linux-repo/apt stable main" | sudo tee /etc/apt/sources.list.d/devlogbus.list
sudo apt update
sudo apt install devlogbus
```

The APT repository metadata is still signed. Users who want signature checks can
install the key and switch the source to `signed-by`:

```bash
curl -fsSL https://dan-sherwin.github.io/devlogbus-linux-repo/keys/devlogbus-archive-key.asc | sudo gpg --dearmor -o /usr/share/keyrings/devlogbus-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/devlogbus-archive-keyring.gpg] https://dan-sherwin.github.io/devlogbus-linux-repo/apt stable main" | sudo tee /etc/apt/sources.list.d/devlogbus.list
```

## Fedora / RHEL / openSUSE

```bash
sudo curl -fsSL -o /etc/yum.repos.d/devlogbus.repo https://dan-sherwin.github.io/devlogbus-linux-repo/rpm/devlogbus.repo
sudo dnf install devlogbus
```

Use the same repository file under `/etc/zypp/repos.d/devlogbus.repo` and run
`sudo zypper install devlogbus` on openSUSE.

The RPM packages and repository metadata are still signed. Users who want
signature checks can import the key and set `gpgcheck=1` and
`repo_gpgcheck=1` in the repository file:

```bash
sudo rpm --import https://dan-sherwin.github.io/devlogbus-linux-repo/keys/devlogbus-archive-key.asc
```

## Alpine Linux

```sh
echo "https://dan-sherwin.github.io/devlogbus-linux-repo/alpine/$(apk --print-arch)" | sudo tee -a /etc/apk/repositories
sudo apk update
sudo apk add --allow-untrusted devlogbus
```

The Alpine index is still signed. Users who want signature checks can install
the public key and omit `--allow-untrusted`:

```sh
sudo wget -O /etc/apk/keys/devlogbus@dan-sherwin.rsa.pub https://dan-sherwin.github.io/devlogbus-linux-repo/keys/devlogbus@dan-sherwin.rsa.pub
sudo apk add devlogbus
```

## Signing Keys

- APT/RPM GPG fingerprint: `BE890A0D4072D25B97D7F84D2BDF255EF7EE0C9B`
- Alpine public key: `devlogbus@dan-sherwin.rsa.pub`

## Current Version

`devlogbus 1.3.1`
