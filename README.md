# CTF Walkthroughs

> Curated security-learning notes focused on methodology, enumeration discipline, and clear reporting.

[![Status](https://img.shields.io/badge/status-learning_notes-0f766e)](#)
[![Focus](https://img.shields.io/badge/focus-methodology-1d4ed8)](#)
[![Ethics](https://img.shields.io/badge/scope-authorized_labs-111827)](#)

This repository contains a small set of CTF walkthroughs and notes from authorized training labs.

It is intentionally not a large collection of copied answers. The goal is to show how I approach security problems: enumerate carefully, validate assumptions, document the attack path, and explain the lesson learned.

## Why This Repo Exists

My main portfolio focus is AI automation, e-commerce systems, and industrial software. This CTF repo supports that profile by showing security awareness and disciplined debugging, not by trying to become a cybersecurity content farm.

## Writeup Style

The format is based on common CTF writeup conventions used across Hack The Box, TryHackMe, and public security blogs:

1. Scope and target summary.
2. Enumeration.
3. Attack path.
4. Privilege escalation reasoning.
5. Lessons learned.
6. Redacted flags and secrets.

## Walkthroughs

| Lab | Focus | Status |
| --- | --- | --- |
| [Silver Platter](sliver-platter/README.md) | Web app auth bypass, IDOR, log review, Docker credential discovery | Sanitized |
| [Pyrat](pyrat/README.md) | Python service enumeration, interpreter behavior, source discovery attempts | Sanitized notes |

## Methodology

See [methodology.md](methodology.md).

## Ethics

All notes are for authorized CTF environments only. Do not use these techniques on systems you do not own or have explicit permission to test.
