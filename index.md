---
description: Secure data transfer using age encryption and OneDrive
layout: default
title: Data Transfer System
---

```{=html}
<style>
/* Floating TOC */
#markdown-toc {
  position: fixed;
  right: 40px;
  top: 140px;
  width: 260px;
  max-height: 70vh;
  overflow: auto;
  padding: 15px;
  background: #f8f9fa;
  border: 1px solid #e1e4e8;
  border-radius: 8px;
  font-size: 0.9em;
}
@media (max-width: 1200px) {
  #markdown-toc {
    position: relative;
    width: 100%;
    right: auto;
    top: auto;
    margin-bottom: 20px;
  }
}
.banner {
  width: 100%;
  border-radius: 12px;
  margin-bottom: 20px;
}
.logo {
  height: 80px;
  margin-bottom: 10px;
}
</style>
```
`<img src="/assets/logo.png" alt="Epigenica Logo" class="logo"/>`{=html}

`<img src="/assets/banner_header.jpg" alt="Data Transfer Banner" class="banner"/>`{=html}

# Secure Data Transfer System

Welcome to the secure file transfer documentation for encrypted data
exchange using **age** and **OneDrive**.

------------------------------------------------------------------------

## Table of Contents

{:toc}

------------------------------------------------------------------------

## Overview

This system ensures secure transfer of sensitive data using file-level
encryption before upload to OneDrive.

Key features:

-   Strong public-key encryption (`age`)
-   Secure upload to OneDrive (max 250 GB per file)
-   Local decryption only by authorized users
-   Multi-recipient support

------------------------------------------------------------------------

## 1. Install `age`

### macOS

``` bash
brew install age
```

### Ubuntu / Debian

``` bash
sudo apt update
sudo apt install age
```

### Windows

Download from: https://github.com/FiloSottile/age/releases

Verify installation:

``` bash
age --version
```

------------------------------------------------------------------------

## 2. Generate Encryption Key (One-Time)

``` bash
age-keygen -o key.txt
```

Keep `key.txt` secure. Never upload private keys.

------------------------------------------------------------------------

## 3. Encrypt Before Upload

``` bash
age -r age1PUBLICKEY -o file.fastq.gz.age file.fastq.gz
```

Upload only the `.age` file to OneDrive.

------------------------------------------------------------------------

## 4. Upload to OneDrive

-   Maximum file size: **250 GB**
-   Share download link separately
-   Share public keys securely

------------------------------------------------------------------------

## 5. Download and Decrypt

``` bash
age -d -i key.txt -o file.fastq.gz file.fastq.gz.age
```

Verify integrity after decryption.

------------------------------------------------------------------------

## 6. Multi-Recipient Encryption

``` bash
age -r age1KEY1 -r age1KEY2 -o file.age file
```

------------------------------------------------------------------------

## Security Best Practices

-   Never upload private keys
-   Exchange public keys securely
-   Delete unencrypted temporary files
-   Store private keys in encrypted storage

------------------------------------------------------------------------

© Epigenica AB -- Secure Data Transfer System
