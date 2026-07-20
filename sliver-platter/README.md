# Silver Platter

> Authorized CTF walkthrough focused on web application enumeration, access control issues, and privilege escalation through operational logs.

## Summary

Silver Platter exposed a web application on a non-standard port. The path to compromise came from careful web enumeration, authentication weakness research, message/notification review, and post-compromise log analysis.

This public version redacts flags, passwords, and lab-specific secrets.

## Services

| Port | Service | Observation |
| --- | --- | --- |
| 22 | SSH | OpenSSH on Ubuntu |
| 80 | HTTP | Nginx |
| 8080 | HTTP proxy / web app | Silverpeas login portal |

## Enumeration Notes

The first useful signal was the application path:

```text
http://<target>:8080/silverpeas/
```

From there, the investigation moved into:

- Identifying the application and version family.
- Searching for known authentication and XSS issues.
- Reviewing available authenticated areas after access.
- Checking notifications and object references for authorization gaps.

## Attack Path

1. Discover exposed Silverpeas login.
2. Research known authentication weakness affecting the target.
3. Gain application access in the lab environment.
4. Review notifications and internal references.
5. Identify an IDOR-style weakness that exposed SSH entry material.
6. Use SSH to gain a low-privileged shell.

## Privilege Escalation

After login, the user belonged to a monitoring-related group with access to log files. Reviewing historical logs revealed operational command history involving container startup parameters.

The important lesson was not the credential itself, but the class of issue:

- Logs can expose deployment commands.
- Deployment commands can expose environment variables.
- Environment variables can contain service passwords.
- Service passwords can become privilege escalation pivots.

## Lessons Learned

- Non-standard web ports deserve the same attention as port 80/443.
- Application notifications can expose sensitive object references.
- Group membership matters during post-exploitation.
- Logs are often a high-value target in CTFs and real systems.
- Deployment secrets should never appear in shell history, logs, or command output.

## Remediation Perspective

- Patch known application vulnerabilities.
- Enforce object-level authorization checks.
- Avoid secrets in command-line arguments.
- Restrict log access.
- Rotate credentials after exposure.

## Flags

Flags are intentionally redacted in this public version.
