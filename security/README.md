# AI Security Skill

## Overview

The AI Security skill identifies security vulnerabilities in AI and LLM applications. It focuses on **SECURITY EXPLOITS** that attackers could use to compromise systems, steal data, or cause harm.

## Complementary to AI Safety Skill

- **AI Security** (this skill) → Security vulnerabilities, exploits, data breaches
- **AI Safety** (separate skill) → Ethical harm, vulnerable populations, bias

## What It Checks For

### Critical Security Categories

1. **Prompt Injection (OWASP LLM01)**
   - Direct prompt injection (jailbreaking)
   - Indirect prompt injection (malicious external content)
   - System prompt extraction

2. **Hardcoded Secrets & API Keys**
   - OpenAI, Anthropic, AWS, Google Cloud API keys
   - Database credentials
   - JWT secrets, OAuth tokens
   - Stripe and payment keys
   - Private SSH keys and certificates

3. **Sensitive Data Exposure (OWASP LLM06)**
   - PII in prompts (SSN, email, addresses)
   - Data leakage through logging
   - Insufficient encryption
   - GDPR/HIPAA violations

4. **Insecure Output Handling (OWASP LLM02)**
   - SQL injection via LLM outputs
   - Code execution (exec, eval)
   - XSS via unsanitized HTML
   - Command injection

5. **Supply Chain Vulnerabilities (OWASP LLM03)**
   - Unverified model sources
   - Compromised dependencies
   - Malicious plugins
   - Outdated packages

6. **Excessive Agency & Permissions**
   - Autonomous destructive actions
   - Over-privileged LLMs
   - No user confirmation
   - Missing rate limits

7. **Additional Risks**
   - RAG poisoning
   - Insufficient logging/monitoring
   - Insecure configurations
   - DoS vulnerabilities

## How to Use

Simply paste your code and ask Claude to review it:

```
"Check this code for security issues"
"Review for vulnerabilities"
"Is this secure?"
```

The skill automatically activates and provides:
- **Vulnerability type** (from OWASP LLM Top 10)
- **Severity level** (Critical → Low)
- **Attack scenario** (how it could be exploited)
- **Impact assessment** (data breach, cost, compromise)
- **Concrete mitigations** (code fixes)

## Evaluation Tests

The skill includes **18 comprehensive test cases** covering:

1. Hardcoded OpenAI API key (CRITICAL)
2. Basic prompt injection (HIGH)
3. SQL injection via LLM (CRITICAL)
4. PII in prompts (HIGH)
5. Hardcoded AWS credentials (CRITICAL)
6. Code execution from LLM output (CRITICAL)
7. Database connection string with password (CRITICAL)
8. XSS via LLM output (HIGH/CRITICAL)
9. Indirect prompt injection (HIGH)
10. Excessive LLM permissions (HIGH/CRITICAL)
11. No rate limiting (MEDIUM/HIGH)
12. API key in frontend code (CRITICAL)
13. Logging sensitive data (HIGH)
14. Unverified model source (MEDIUM/HIGH)
15. Hardcoded Stripe live key (CRITICAL)
16. RAG without sanitization (MEDIUM/HIGH)
17. Hardcoded JWT secret (CRITICAL)
18. Safe implementation (LOW/secure - baseline)

## Security Frameworks Referenced

- **OWASP LLM Top 10 (2025)** - Core framework for LLM security
- **CWE** - Common Weakness Enumeration
- **NIST AI RMF** - AI risk management
- **GDPR** - EU data protection
- **HIPAA** - Healthcare data privacy
- **PCI DSS** - Payment card security
- **ISO 27001** - Information security

## Recommended Security Tools

**Secrets Scanning:**
- GitGuardian
- TruffleHog
- Gitleaks
- GitHub Secret Scanning

**Prompt Injection Testing:**
- Promptfoo
- OWASP LLM test suites

**Dependency Scanning:**
- Dependabot
- Snyk
- OWASP Dependency-Check

**Static Analysis:**
- Semgrep
- CodeQL
- Bandit (Python)

## When This Skill Triggers

Automatically activates when:
- Reviewing code with AI/LLM integrations
- Code contains API calls, database connections
- User asks for security review
- Analyzing authentication/authorization code
- Reviewing configuration files

## Installation

1. Download skill files
2. Copy to `/mnt/skills/user/ai-security/`
3. Upload `SKILL.md` and `evals/evals.json`
4. Skill activates automatically!

See `INSTALL.md` for detailed instructions.

## Examples

**Input:**
```python
openai.api_key = "sk-proj-abc123"
```

**Output:**
```
⚠️ CRITICAL SECURITY VULNERABILITY

Type: Hardcoded API Key (CWE-798)
Severity: CRITICAL

Issue: OpenAI API key is hardcoded in source code

Attack Scenario:
1. Attacker finds code in repository
2. Extracts API key
3. Makes unlimited API calls
4. Runs up massive bills or steals data

Impact: Complete API compromise, financial loss, data theft

Mitigation:
```python
import os
openai.api_key = os.getenv('OPENAI_API_KEY')
```

Required Actions:
1. Rotate this key immediately at https://platform.openai.com
2. Add .env to .gitignore
3. Use environment variables or secrets manager
4. Implement pre-commit hooks to block secrets
```

## Important Notes

This skill focuses on **security vulnerabilities**. For ethical safety concerns (harm to children, healthcare safety, bias), use the **ai-safety-checker** skill.

Security issues are typically exploited by **attackers** to:
- Steal data
- Compromise systems
- Incur costs
- Gain unauthorized access

## Contributing

Found a new vulnerability pattern? Want to improve detection? Contributions welcome!

## License

[Specify your license - MIT, Apache 2.0, etc.]

## Credits

Created by: Mike
Based on: OWASP LLM Top 10, CWE, security research and real-world incidents
