# Verifying integrity of QRL Wallet releases

Requirements

- shasum
- gpg

## 1. Download a QRL wallet

These are found on the Gihub releases page: [https://github.com/theQRL/qrl-wallet/releases](https://github.com/theQRL/qrl-wallet/releases)

## 2. Download security@theqrl.org GPG public key

Either from key servers or [Github](https://github.com/theQRL/security/blob/master/security.theqrl.org.gpg.asc)

e.g.:

**Either:**

```
curl https://raw.githubusercontent.com/theQRL/security/master/security.theqrl.org.gpg.asc | gpg --import
```

**or:**

```
gpg --search-keys security@theqrl.org
```
should yield:

> gpg: data source: https://keys.openpgp.org:443
(1)  Security team <security@theqrl.org>
    4096 bit RSA key 14762269BFDD11F3, created: 2019-02-16

selecting key 1 will add the key to your keychain

## 3. Download SHASUM file for the OS/version of wallet release

- [v1.8.1](1.8.1)
- [v1.8.0](1.8.0)
- [v1.7.3](1.7.3)
- [v1.7.0](1.7.0)
- [v1.6.6](1.6.6)

## 4. Verify the signaure of the SHASUM file

```
gpg --verify LINUX-x64_QRL-Wallet_1.8.0.deb.shasum.asc
```

Successful verification is indicated by:

```
gpg: Good signature from "Security team <security@theqrl.org>"
```

## 5. Check the SHASUM of the downloaded wallet package

```
shasum -a 512 --check LINUX-x64_QRL-Wallet_1.8.0.deb.shasum.asc
```

Successful verification is indicated by (in this example):

```
LINUX-x64_QRL-Wallet_1.8.0.deb: OK
```

NB: _shasum: WARNING: 19 lines are improperly formatted_ messages are expected and are **not** errors: this is due to the SHASUM file being signed with GPG
