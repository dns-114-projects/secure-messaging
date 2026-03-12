# Secure Messaging

End-to-end encrypted chat with **AES-128-GCM**, 
RSA-PSS message signatures, multi-session support, 
server-side audit log, and a dark-mode web UI.
The project is part of an educational TP whose goal is 
to practice designing and implementing a hybrid RSA + AES 
secure messaging system.

> There is two versions [version1 ; version2]

---

## Overview

Version 2 extends the initial RSA + AES hybrid system 
by adding authenticated encryption (AES-GCM with integrity tag), 
RSA-PSS signatures on every message (non-repudiation), 
per-peer session keys (multi-session), idempotent session 
handling with proper HTTP error codes, a server-side audit log, 
and a richer UI with timestamps, signature badges, and a status panel.
