# Midnight Arcvale — Notes

This document contains internal notes and design decisions for the Midnight Arcvale project.

---

## Purpose

Midnight Arcvale is intended to operate as a Base-first application, with explicit support for:
- Base Mainnet
- Base Sepolia (testnet)

All network-specific configuration is centralized in `config/base.networks.json`.

---

## Network Configuration

The `base.networks.json` file defines:
- Supported Base networks
- Chain IDs
- Default and fallback RPC endpoints
- Block explorer URLs
- Testnet flags

This allows the application to:
- Switch networks deterministically
- Avoid hardcoded RPC URLs in code
- Support future Base networks with minimal changes

---

## Design Principles

- **Static config over code logic**  
  Network metadata should live in JSON, not be scattered across TS files.

- **Safe defaults**  
  Mainnet is the default network, with conservative confirmation counts.

- **Extensibility**  
  Additional Base networks or custom RPCs can be added without refactoring.

---

## Future Improvements

- Add optional `envOverrides` section for custom RPC URLs
- Introduce JSON schema validation in CI
- Expand explorer metadata (API endpoints, rate limits)

---

_Last updated: initial scaffold_
