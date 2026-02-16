# Secure File Transfer Guide Using `age` and SharePoint

This repository contains comprehensive guides for securely transferring files using encryption.

------------------------------------------------------------------------

## Available Methods

### Method 1: Compression + Encryption (Passphrase Mode) - RECOMMENDED

This guide explains how to securely:
- Compress and encrypt a folder using a passphrase
- Decrypt and extract the folder
- Handle passphrase sharing securely

This method is designed for transferring large folders (e.g., sequencing data) via SharePoint.

See separate guides for:
- **Upload Guide**: Instructions for senders
- **Download Guide**: Instructions for recipients

### Method 2: Public Key Encryption (Legacy)

Traditional age encryption using public/private key pairs. See the Legacy Guide for details.

------------------------------------------------------------------------

# Compression + Encryption Guide (Passphrase Mode)

## 1️⃣ Sender Instructions

### Compress + Encrypt (Passphrase Mode)

This method compresses and encrypts in a single step without creating an unencrypted archive on disk.

```bash
tar -czf - folder_name/ | age -p -o folder_name.tar.gz.age
```

You will be prompted to enter a passphrase.

### Important:
- Use a strong passphrase (20+ random characters).
- Do NOT reuse passphrases.
- Do NOT store the passphrase in the same location as the file.

After encryption, upload:
```
folder_name.tar.gz.age
```
to SharePoint.

------------------------------------------------------------------------

## 2️⃣ Passphrase Sharing Policy

The passphrase will be sent in a separate email.

- The email will contain a passphrase valid for a limited duration.
- Customers may reply using secure email practices.
- The encrypted file and passphrase must NEVER be sent in the same message.

Recommended practice:
- Delete the passphrase email after use.
- Do not forward passphrases.
- Store passphrases temporarily only.

------------------------------------------------------------------------

## 3️⃣ Recipient Instructions

### Decrypt + Extract

To decrypt and extract in one step:

```bash
age -d folder_name.tar.gz.age | tar -xzf -
```

You will be prompted to enter the passphrase.

After successful extraction:
- Verify the folder contents.
- Delete the encrypted file if required by policy.

------------------------------------------------------------------------

## Alternative (Two-Step Decryption)

If preferred, decrypt first:

```bash
age -d -o folder_name.tar.gz folder_name.tar.gz.age
```

Then extract:

```bash
tar -xzf folder_name.tar.gz
```

After extraction, securely delete the `.tar.gz` file if required.

------------------------------------------------------------------------

# Security Notes

- Never upload unencrypted data.
- Never store passphrases permanently in plaintext files.
- Use strong, randomly generated passphrases.
- Delete temporary decrypted archives when finished.

------------------------------------------------------------------------

© Secure Data Transfer Instructions
