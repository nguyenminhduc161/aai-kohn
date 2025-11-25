# AAI Services – Clone & Checkout Guide

A clean and simple guide to clone the required **ONAP AAI services** and switch all repositories to the correct branch (`oslo`).

---

## 📚 Table of Contents
- [AAI Components](#aai-components)
- [Clone All Services](#clone-all-services)
- [Checkout to Branch `oslo`](#checkout-to-branch-oslo)
- [Directory Structure](#directory-structure)
- [Notes](#notes)

---

## 🔧 AAI Components

The following AAI repositories will be cloned:

- `aai-common`
- `schema-service`
- `resources`
- `traversal`
- `graphadmin`
- `logging-service`

---

## 🔽 Clone All Services

Run the script below to clone all services:

```bash
for f in aai-common schema-service resources traversal graphadmin logging-service; do 
  git clone https://gerrit.onap.org/r/aai/$f
done
```

---


## 🌿 Checkout All Services to Branch oslo

This script automatically enters each directory, performs a checkout to the oslo branch, and logs the output to checkoutlog.txt.

```bash
for f in aai-common schema-service resources traversal graphadmin logging-service; do
  (
    cd "$f"
    git checkout oslo
  )
done | tee checkoutlog.txt
```
