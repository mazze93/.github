# Security Policy

## Overview

This security policy establishes guidelines for vulnerability disclosure, incident response, and security practices across my GitHub repositories at [@mazze93](https://github.com/mazze93). I maintain these projects with a commitment to security best practices, privacy-first design, and responsible disclosure.

As an individual open-source developer and security engineer, I take security seriously and welcome collaboration from the security research community to identify and address vulnerabilities.

## Scope

This security policy applies to all public repositories under my GitHub account, including:

- Security tools and automation scripts
- Web applications and APIs
- Open-source libraries and utilities
- Documentation and technical writing projects
- Personal projects and experimental code

## Supported Versions

| Version | Supported |
|---|---|
| Main/Production Branch | ✅ |
| Latest Release | ✅ |
| Release − 1 | ✅ |
| Older Releases | ❌ |
| Development/Beta Branches | Limited support |

For projects with specific version support policies, please refer to the individual repository documentation.

## Reporting a Vulnerability

### Security Contact

I encourage responsible disclosure of security vulnerabilities. If you discover a security issue in any of my projects, please report it through one of the following channels:

- **Primary:** GitHub Security Advisory (private vulnerability reporting — preferred). Navigate to the repository's **Security** tab → **Advisories** → **Report a vulnerability**.
- **Alternative:** Direct email to the security contact listed in the repository README.
- **PGP:** For sensitive disclosures, PGP-encrypted email is welcome (key available on request).

### What to Include in Your Report

1. **Description of the vulnerability** — clear explanation of the security issue and its potential impact
2. **Affected versions** — specific versions, branches, or components affected
3. **Attack vector** — how the vulnerability could be exploited
4. **Proof of Concept (PoC)** — reproducible steps or code demonstrating the vulnerability
5. **Impact assessment** — potential consequences for users, data, or infrastructure
6. **Proposed remediation** — suggested fixes or mitigations (optional but appreciated)
7. **CVE request** — whether you plan to request a CVE identifier
8. **Disclosure timeline** — your preferred disclosure timeline or deadline

Please avoid disclosing sensitive vulnerability details in public issues, pull requests, or community forums until we have coordinated disclosure.

### What Not to Report

The following are generally outside the scope of this security program:

- Vulnerabilities in third-party dependencies (report to upstream maintainers)
- Social engineering attacks
- Physical security issues
- Denial of Service (DoS) attacks without demonstrable impact
- Issues in deprecated or unsupported versions
- Theoretical vulnerabilities without proof of exploitability

If you are unsure whether an issue qualifies, please report it and I will make the determination.

## Coordinated Vulnerability Disclosure Process

My projects follow a **Coordinated Vulnerability Disclosure (CVD)** approach that balances transparency with responsible handling of security issues.

### My Commitment to Reporters

- **Acknowledgment within 72 hours** — initial response confirming receipt of your report
- **Status updates as progress is made** — communication on remediation progress
- **Collaborative approach** — opportunity to discuss patches or validation testing
- **Public recognition** — credit in security advisories and release notes (unless you prefer anonymity)
- **Safe harbor** — no legal action for good-faith security research

### Disclosure Timeline

| Timeframe | Action |
|---|---|
| Day 0 | Vulnerability reported via GitHub Security Advisory or email |
| Day 0–3 | Acknowledgment sent to reporter |
| Day 3–14 | Validation and impact assessment |
| Day 14–90 | Patch development and testing |
| Day 90 | Default public disclosure deadline |
| Post-patch | Public disclosure via GitHub Security Advisory |

- **Accelerated disclosure:** for critical vulnerabilities with active exploitation or significant impact, I may expedite the timeline with your agreement.
- **Extended disclosure:** if I need additional time beyond 90 days, I'll communicate this and provide progress updates. Public disclosure will occur at 90 days unless you agree to an extension.
- **Early disclosure:** I may disclose earlier than 90 days if a patch is available and stable, with your agreement.

### CVE Assignment

For eligible vulnerabilities, I will request CVE assignment through the GitHub Security Advisory system or MITRE directly. CVE publication timing will be coordinated with the public disclosure schedule.

## Security Standards and Best Practices

My security practices align with recognized industry frameworks and standards:

- NIST Cybersecurity Framework (CSF) Core Functions
- OWASP Top 10 Web Application Security Risks
- CIS Controls for Effective Cyber Defense
- OpenSSF Best Practices Badge criteria
- ISO/IEC 27001 information security principles

## Security Features and Controls

### Repository Security

My repositories implement the following security controls where applicable:

- **Branch protection** — main branches protected with required reviews and status checks
- **Secret scanning** — automated detection of exposed credentials and API keys (GitHub native)
- **Dependabot alerts** — automated vulnerability scanning and dependency updates
- **Code scanning** — CodeQL or similar SAST tools for vulnerability detection
- **Signed commits** — GPG/SSH commit signing for authenticity verification
- **Two-factor authentication** — enabled on my GitHub account with hardware security keys
- **Access control** — principle of least privilege for collaborators

### CI/CD Pipeline Security

- SHA-pinned action versions for supply chain security
- Minimal workflow permissions with explicit grants
- Isolated execution for untrusted code (fork pull requests)
- Secret management through GitHub Secrets and environment protection
- Artifact signing and SLSA provenance where applicable

### Dependency Management

- Automated dependency updates via Dependabot
- Vulnerability scanning with severity threshold enforcement
- SBOM (Software Bill of Materials) generation
- License compliance verification
- Regular manual audit of critical dependencies

## Incident Response

### Severity Classification

| Severity | Impact | Response time |
|---|---|---|
| Critical | Data breach, RCE, authentication bypass | 24 hours |
| High | Widespread data exposure, privilege escalation | 72 hours |
| Medium | Limited exposure, moderate-impact vulnerabilities | 14 days |
| Low | Minimal impact, edge cases, theoretical issues | 30 days |

### Notification Procedures

In the event of a confirmed security incident affecting users:

1. **Immediate containment** — stop active exploitation and secure affected systems
2. **Impact assessment** — determine scope of affected users and data
3. **User notification** — alert affected parties via GitHub Security Advisories and repository announcements
4. **Remediation deployment** — release patches and security updates
5. **Post-incident review** — conduct retrospective and update security controls
6. **Public disclosure** — publish security advisory with timeline, impact, and remediation steps

## Safe Harbor Policy

I am committed to protecting security researchers who report vulnerabilities in good faith. I will not pursue legal action against researchers who:

- Report vulnerabilities responsibly through designated channels
- Avoid intentional harm to users, data, or infrastructure
- Do not publicly disclose vulnerabilities before coordinated disclosure
- Respect user privacy and data confidentiality
- Comply with applicable laws during security research

I encourage security research that helps improve the security and reliability of open-source software.

## Security Best Practices for Contributors

### For Code Contributors

- Never commit credentials, API keys, or sensitive data to repositories
- Use environment variables or GitHub Secrets for configuration
- Follow secure coding guidelines for the relevant language/framework
- Include security considerations in pull request descriptions
- Run security scanners locally before submitting pull requests
- Sign all commits with GPG or SSH keys

### For Maintainers and Collaborators

- Review all code changes for security implications
- Respect branch protection rules and required status checks
- Rotate SSH keys and Personal Access Tokens regularly (recommended: every 90 days)
- Monitor repository activity and respond to security alerts
- Address Dependabot and code scanning alerts promptly
- Maintain secure development environments
- Use hardware security keys for 2FA when possible

## Security Resources

**Documentation**

- [OWASP Secure Coding Practices](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)
- [GitHub Security Best Practices](https://docs.github.com/en/code-security)
- [OpenSSF Best Practices](https://bestpractices.coreinfrastructure.org/)

**Security Tools**

- GitHub security features (Dependabot, secret scanning, code scanning)
- CodeQL for semantic code analysis
- git-secrets / gitleaks for credential detection
- SAST/DAST tools for application security testing
- Trivy or Grype for container scanning

## Updates to This Policy

This security policy is reviewed and updated periodically in response to emerging threats, best-practice evolution, or community feedback. Material changes will be announced through GitHub repository commits and releases, and security advisories for significant policy updates. Version history is maintained in the repository commit history.

## Contact Information

- **GitHub:** [@mazze93](https://github.com/mazze93)
- **Security reports:** GitHub Security Advisories (preferred) or the email contact in the repository README
- **PGP key:** available on request for sensitive communications
- **Response time:** I aim to acknowledge reports within 72 hours and provide updates as progress is made

## Acknowledgments

I am grateful to security researchers and community members who help improve the security of my projects. Vulnerability reports that lead to security improvements will be acknowledged in security advisories and release notes (unless anonymity is preferred).

## Legal Considerations

This security policy reflects my commitment to responsible vulnerability disclosure and open-source security best practices.

All security research and vulnerability reporting must comply with applicable laws, including the Computer Fraud and Abuse Act (CFAA), Digital Millennium Copyright Act (DMCA), and international equivalents. This safe harbor policy is contingent on good-faith security research conducted within legal boundaries.

For projects involving user data, please refer to individual repository documentation regarding data handling and privacy practices.

---

**Policy version:** 2.0.0 (Personal Projects Edition) · **Last updated:** 2026-02-01 · **Policy owner:** [@mazze93](https://github.com/mazze93)

*Based on security best practices from OWASP, OpenSSF, GitHub, and NIST.*
