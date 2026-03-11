# Secure Communications & Encrypted Messaging

**Projet Cybersécurité / Cryptographie appliquée** | école d'ingénieurs — Nov.–Déc. 2025 | Python, Flask

## Présentation

Conception d'une messagerie sécurisée client/serveur. Chaque message est chiffré avec une clé de session AES, transmise de façon sécurisée via RSA par un serveur de confiance.

## Architecture

```
 Client A                  Serveur                Client B
 gen RSA (pub/priv)    → reçoit clés publiques  ← gen RSA (pub/priv)
                          gen clé AES session
                          chiffre AES avec RSA-A et RSA-B
 clé AES (déchiffrée) ←  envoie                → clé AES (déchiffrée)
          ←———— messages chiffrés AES directement ————→
```

## Protocoles implémentés

| Partie | Contenu |
|:---|:---|
| **P1** | Échange Diffie-Hellman → secret partagé `k`, chiffrement clé AES-128 par XOR avec `k`, intégrité SHA-256 |
| **P2** | Communication client/serveur chiffrée RSA via Flask/HTTP |
| **P3** | Attaque MITM avec `mitmproxy` : interception + modification de messages |
| **P4** | Signature numérique RSA côté client : triplet (message chiffré + signature + clé publique) |
| **P5** | Attaques par usurpation : remplacement clé publique seule, puis remplacement complet |

## Mini-projet — Messagerie complète

- Chaque client génère une paire RSA et s'enregistre auprès du serveur
- Serveur distribue la clé AES de session chiffrée pour chaque client
- Communication directe client-à-client chiffrée AES
- Interface HTML simple pour la saisie et l'affichage
- Affichage clair/chiffré dans le terminal

## Stack

`Python` · `Flask` · `cryptography` · `mitmproxy`

---

*Projet académique — école d'ingénieurs*
