# Security Policy

## 1. Security Commitment

The security of helancode and its users is a priority.

helancode is an AI-powered coding harness that may interact with local filesystems, shell commands, external processes, model providers, and third-party tools.

Security vulnerabilities can potentially affect the host environment, source code, credentials, and other sensitive resources.

We encourage responsible security research and coordinated vulnerability disclosure.

## 2. Supported Versions

Security fixes are prioritized for actively maintained releases.

| Version | Security Support |
|---|---|
| Latest stable release | Supported |
| Previous stable release | Best effort |
| Development branch | Best effort |
| Older releases | Not guaranteed |

Maintainers may revise this policy as the project matures.

## 3. Reporting a Vulnerability

**Do not report security vulnerabilities through public GitHub issues, discussions, or pull requests.**

Instead, use one of the following private reporting channels:

### Preferred: GitHub Private Vulnerability Reporting

[Report a vulnerability privately](https://github.com/Emmanuel-Arokiaraj/helancode/security/advisories/new)

### Alternative: Email

[SECURITY_CONTACT_EMAIL]

If private reporting is unavailable, contact the maintainers directly using the security contact above.

## 4. Information to Include

When reporting a vulnerability, provide as much of the following information as possible:

- Vulnerability description.
- Affected component or module.
- Affected version or commit.
- Steps to reproduce.
- Proof of concept, if available.
- Expected security impact.
- Potential attack scenarios.
- Suggested mitigation, if known.

Avoid including real credentials, API keys, personal information, or private source code in the report.

Use synthetic data in proof-of-concept demonstrations wherever possible.

## 5. Security Scope

The following areas are particularly relevant to this project.

### Runtime and Process Execution

- Arbitrary command execution.
- Command injection.
- Unsafe process spawning.
- Privilege escalation.
- Insecure environment variable handling.
- Improper process isolation.

### Filesystem Access

- Path traversal.
- Unauthorized file modification.
- Symlink-related vulnerabilities.
- Unexpected access outside permitted directories.
- Unsafe file operations.

### AI and Prompt Injection

- Prompt injection leading to unauthorized tool execution.
- Improper trust boundaries between model output and application logic.
- Bypassing tool permissions or approval mechanisms.
- Unsafe handling of untrusted repository content.
- Unauthorized access to sensitive context.

### Credentials and Secrets

- API key exposure.
- Token leakage.
- Sensitive information in logs.
- Insecure credential storage.
- Accidental disclosure through model requests.

### Network and External Integrations

- Server-side request forgery where applicable.
- Insecure TLS configuration.
- Authentication or authorization bypasses.
- Unsafe handling of external responses.
- Vulnerabilities in provider and tool integrations.

### Dependencies and Supply Chain

- Vulnerable dependencies.
- Malicious dependency introduction.
- Dependency confusion.
- Unsafe build or installation procedures.

## 6. Out of Scope

The following are generally not considered vulnerabilities without an additional security impact:

- Issues requiring an attacker to already have unrestricted local administrative access.
- Expected execution of commands explicitly authorized by the user.
- Model-generated incorrect code without an associated security boundary failure.
- Prompt injection demonstrations that do not establish a security impact.
- Vulnerabilities in third-party services outside this project's control.
- Vulnerabilities in unsupported or obsolete releases that have already been superseded, unless they also affect supported releases.

This list does not prevent maintainers from investigating other security concerns.

## 7. Disclosure Process

We follow a coordinated disclosure approach.

1. The report is received through a private channel.
2. Maintainers acknowledge and assess the report.
3. The vulnerability is reproduced and its impact evaluated.
4. A fix or mitigation is developed.
5. A patched release is prepared where applicable.
6. Disclosure is coordinated with the reporter.

We aim to acknowledge reports within 7 calendar days and provide an initial assessment within 14 calendar days.

These are response targets, not guaranteed resolution deadlines.

## 8. Responsible Research

Security researchers must:

- Avoid accessing, modifying, or destroying other people's data.
- Avoid disrupting services or infrastructure.
- Avoid testing against systems without authorization.
- Avoid exposing vulnerability details publicly before coordinated disclosure.
- Provide reasonable time for maintainers to investigate and address the issue.

Do not use real user credentials or private repositories during testing.

## 9. Security Disclaimer

**helancode** provides tools that can interact with a developer's local environment.

Users remain responsible for reviewing tool permissions, execution approvals, filesystem access, environment configuration, and the consequences of commands they authorize.

No software can guarantee complete protection against malicious input, compromised dependencies, model-generated instructions, or vulnerabilities in external systems.

Security features should reduce risk, not be interpreted as a guarantee of isolation or safety.

## 10. Contact

Security reports:

- GitHub: https://github.com/Emmanuel-Arokiaraj/helancode/security/advisories/new
- Email: [Emmanuel-Arokiaraj](mailto:aemmanuel685210@gmail.com)

Thank you for helping keep **helancode** and its users secure.
