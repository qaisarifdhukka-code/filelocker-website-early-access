---
layout: ../../layouts/DocsLayout.astro
title: FileLocker Security Architecture
description: FileLocker is designed around local file processing and password-based encryption.
---

# FileLocker Security Architecture

FileLocker is designed around local file processing and password-based encryption.

## 1. File selection
You select the file or folder you want to protect.

## 2. Local processing
FileLocker processes the selected content on your device. The normal locking workflow does not require uploading the original file to a FileLocker cloud service.

## 3. Password processing
The password is processed using Argon2id as part of the key-derivation process. Argon2id is designed to make password-guessing attacks more computationally expensive.

## 4. Encryption
FileLocker uses AES-256-GCM to protect the file contents. AES-256-GCM provides both confidentiality and authenticated encryption.

## 5. Protected file creation
FileLocker creates a self-contained protected file that can be delivered to the recipient.

## 6. Delivery
The protected file can be transferred using the method appropriate for your workflow.

## 7. Local browser unlocking
The recipient opens the protected file in a supported browser. The browser performs the decryption locally using supported Web APIs.

## 8. File recovery
After successful authentication and decryption, the recipient saves the recovered file to their device.

## What FileLocker does not do
As part of the normal file protection workflow, FileLocker does not require you to upload the original document to a FileLocker cloud storage service. Your protected files remain under your control.
