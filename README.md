The proper protocol and procedure to convey security matters to the Quantum Resistant Ledger using e2ee securly (though not post-quantum secure) 
is by emailing security@theqrl.org using OpenPGP.

## Instructions

### Thunderbird

**1. Setup private/public key**

1. Open Thunderbird v78 and above
2. Go to Edit -> Account Settings
3. Find the email account you want to use and select [email acct]-> End-to-End Encryption
4. Click [Add Key]
5. Create new OpenPGP key [continue]
6. Define any parameters (defaults are fine), then [Generate Key] and [confirm]

**2. Import security@theqrl.org's public key**

1. Open Thunderbird 78 and above
2. Go to Tools -> OpenPGP key manager
3. Select Edit -> Import Keys from URL
4. Enter URL: `https://raw.githubusercontent.com/theQRL/security/master/security.theqrl.org.gpg.asc`

**3. Sending an End-to-end encrypted message**

1. Open Thunderbird 78 and above
2. Compose a message to security@theqrl.org
3. Select from the dropdown [security], "Require Encryption", and "Attach my public key"
4. Send email.
