# KoBold

A bold key-value store for knowledge and config management

---

## Install

```bash
pip install kobold
```

## Usage

### Setting Arbitrary K-V Pairs

```bash
kb store - set -a=1 -b=2 -c=3
```

### Getting Them

```bash
kb store - get a
```

## What's the '-' for?

Good thing you asked. Underneath the hood, this package uses Python's shelve implementation to create and manage named shelves stored in the user's home directory found at `$HOME/.kobold`.

The '-' is a placeholder for default named shelve ('default').

## Why are named kv stores useful?

Say you worked on multiple AWS accounts that you switched between often.

```bash
echo `kb store aws.env-1 get account_num`
# 1234...

echo `kb store aws.env-2 get account_num`
# 5678...

kb store aws set -envs=1,2,3,4

kb store aws get envs
#[ 1, 2, 3, 4]
```
