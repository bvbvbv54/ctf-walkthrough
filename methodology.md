# CTF Methodology

## 1. Orient

- Identify the target IP, lab name, and rules of engagement.
- Keep notes from the first command.
- Separate facts from assumptions.

## 2. Enumerate

- Start with service discovery.
- Follow up on unusual ports and banners.
- Record versions, paths, usernames, error messages, and exposed files.
- Avoid jumping to exploit code before understanding the service.

## 3. Validate The Attack Path

- Map each finding to a clear hypothesis.
- Test one assumption at a time.
- Prefer manual verification before automated tooling.
- Keep commands reproducible.

## 4. Stabilize Access

- Upgrade shells when appropriate.
- Check user context and group memberships.
- Look for readable config, logs, scheduled jobs, and service files.

## 5. Privilege Escalation

- Enumerate permissions before exploiting.
- Check sudo rights, writable paths, exposed credentials, and service misconfigurations.
- Explain why the escalation works, not just the command that worked.

## 6. Report Cleanly

- Redact flags, passwords, private IPs when publishing.
- Explain the weakness and the fix.
- Keep the writeup educational and ethical.

## References That Inspired The Structure

- Common Hack The Box and TryHackMe writeup formats.
- Public CTF methodology notes that organize work into enumeration, exploitation, post-exploitation, and lessons learned.
- Security reporting conventions that separate impact, evidence, and remediation.
