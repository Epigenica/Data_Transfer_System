# Secure File Transfer Guide Using `age` and OneDrive

This guide explains how to:  
- Install `age` 
- Encrypt files before upload   
- Upload to SharePoint (max 250 GB per file)   
- Download securely   
- Decrypt files   

------------------------------------------------------------------------

# 1. Install `age`

## macOS (Homebrew)

``` bash
brew install age
```

## Ubuntu / Debian

``` bash
sudo apt update
sudo apt install age
```

If not available via apt:

``` bash
sudo snap install age
```

## Windows

Download the latest release from:
https://github.com/FiloSottile/age/releases

Unzip and add the binary to your PATH.

Verify installation:

``` bash
age --version
```

------------------------------------------------------------------------

# 2. Generate Your Encryption Key (One Time Only)

Each user should generate their own key pair.

``` bash
age-keygen -o key.txt
```

This creates: - `key.txt` → your PRIVATE key (keep secret) - A public
key displayed in the terminal (starts with `age1...`)

⚠️ Store `key.txt` securely. Never upload it to OneDrive.

------------------------------------------------------------------------

# 3. Encrypt a File Before Upload

Assume the file is:

    large_data.fastq.gz

Encrypt using the recipient's public key:

``` bash
age -r age1RECIPIENTPUBLICKEY -o large_data.fastq.gz.age large_data.fastq.gz
```

After encryption: - Upload ONLY the `.age` file - Delete the original
file if required by policy

------------------------------------------------------------------------

# 4. Upload to OneDrive

Upload the encrypted file:

    large_data.fastq.gz.age

Notes: - Maximum file size allowed: **250 GB per file** - Do not upload
unencrypted data - Share the download link separately

Share encryption keys via secure channel (e.g., password manager). Never
send private keys via OneDrive.

------------------------------------------------------------------------

# 5. Download the File

Recipient downloads:

    large_data.fastq.gz.age

Place it in a secure working directory.

------------------------------------------------------------------------

# 6. Decrypt the File

Using the private key:

``` bash
age -d -i key.txt -o large_data.fastq.gz large_data.fastq.gz.age
```

After successful decryption: - Verify file integrity - Remove encrypted
file if required

------------------------------------------------------------------------

# 7. Multi-Recipient Encryption (Optional)

If multiple people need access:

``` bash
age -r age1KEY1 -r age1KEY2 -o file.age file
```

Each recipient can decrypt using their own private key.

------------------------------------------------------------------------

# 8. Recommended Workflow Summary

1.  Generate key (one time)
2.  Exchange public keys
3.  Encrypt file
4.  Upload encrypted file to OneDrive (≤ 250 GB)
5.  Share link
6.  Recipient downloads
7.  Recipient decrypts locally

------------------------------------------------------------------------

# Security Best Practices

-   Never upload private keys
-   Never email private keys
-   Use secure password manager for key exchange
-   Delete unencrypted temporary files
-   Store private keys in encrypted disk or password vault

------------------------------------------------------------------------

End of Guide
