# Overall Design

## Overview

"What does dodo say" is a co-chair committee auditable anonymous forums.

## Principles

There are several principles we should always keep following:

- really anonymous
- auditable
- limited number of anonymous identities for one person
- all history of any actions should be recorded

## Technical Path for the Major Features

### Co-chair Committees Auditable Anonymous

Here exist one key pair (Public Key/Private Key) for encryption of the sensible data like the real identity behind the anonymous identity.

It assumes that there are several trustable, respected real-name co-chair committees, and each one of the holds "a piece of the private key".

When enough pieces of the private key are collected, the anonymous identity can be audited.

The core of the implementation is secret sharing, for example, Shamir's Secret Sharing.

Shamir's Secret Sharing has been commonly used like:

- [HashiCorp Vault Shamir seals](https://www.vaultproject.io/docs/concepts/seal#shamir-seals)
- [Trezor Hardware Wallet: Shamir Backup](https://trezor.io/shamir/)

## Components

### Backend API

It's a web server provides HTTP API with the basic functionality as a forum.

We could storage the data based on RDBMS.

### Frontend Single Page Application

It would be a web application which could looks like a forum.

### Command Line Tools for Cryptography Operations

A command line tool is necessary for the following operations:

- keyring related operations

because it seem there no way to do that on webpage.
