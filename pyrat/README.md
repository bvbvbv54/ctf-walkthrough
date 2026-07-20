# Pyrat

> Authorized CTF notes focused on Python service behavior, interpreter exposure, and disciplined dead-end analysis.

## Summary

Pyrat exposed SSH and a Python-backed service on a high port. The challenge was less about a single obvious exploit and more about understanding how the service handled input, what Python context was available, and which leads were real versus dead ends.

This public version redacts credentials, flags, and lab-specific sensitive material.

## Services

| Port | Service | Observation |
| --- | --- | --- |
| 22 | SSH | OpenSSH on Ubuntu |
| 8000 | HTTP-like Python service | Python SimpleHTTP-style banner with interpreter error behavior |

## Enumeration Notes

The service on port `8000` responded to unexpected input with Python errors such as undefined names and syntax failures. That behavior suggested the application was evaluating or interpreting input in a Python context.

Useful checks included:

- Service versioning with Nmap.
- Sending malformed HTTP verbs and custom input.
- Inspecting Python module state where possible.
- Testing whether source code could be recovered.
- Separating useful evidence from dead ends.

## Investigation Path

1. Identify the open services.
2. Notice Python-specific error responses.
3. Test whether input reaches an interpreter-like execution path.
4. Attempt controlled introspection.
5. Explore common filesystem locations.
6. Review readable user/application configuration.
7. Document dead ends instead of hiding them.

## Dead Ends

Some paths did not directly lead to compromise:

- Attempting to recover source through standard inspection.
- Checking common Python installation paths.
- Reviewing unrelated local files.
- Following configuration artifacts that did not produce a usable escalation path.

Keeping these notes is useful because it shows the actual reasoning process, not just the final command.

## Lessons Learned

- Error messages can reveal execution context.
- Python-backed services require careful input testing.
- Introspection is powerful but not always available.
- Dead ends are part of methodical exploitation.
- Public writeups should redact credentials and flags.

## Remediation Perspective

- Never evaluate untrusted input.
- Avoid exposing interpreter errors to users.
- Run services with least privilege.
- Keep credentials out of local config files.
- Restrict access to development artifacts.

## Flags

Flags and credentials are intentionally redacted in this public version.
