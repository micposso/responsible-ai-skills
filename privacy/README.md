# AI Privacy Skill

## Overview

The AI Privacy skill identifies privacy violations and data protection issues in AI/LLM applications. It focuses on **PRIVACY RIGHTS**, user consent, and data protection compliance - not security exploits or ethical safety.

## Skill Separation

**AI Privacy** (this skill):
- Privacy rights and consent
- Biometric data (facial recognition, emotion detection)
- PII collection and use
- Tracking and surveillance
- GDPR, CCPA, BIPA compliance

**AI Security** (different skill):
- Hardcoded secrets and API keys
- Prompt injection attacks
- SQL/XSS injection
- Technical vulnerabilities

**AI Safety** (different skill):
- Harm to vulnerable populations
- Bias and discrimination
- Autonomous decisions causing harm
- Ethical concerns

## What It Checks For

### Critical Privacy Categories

1. **Biometric Data Collection**
   - Facial recognition systems
   - Fingerprint/iris scanning
   - Voice recognition
   - Emotion detection
   - Gait analysis
   - Behavioral biometrics

2. **Personally Identifiable Information (PII)**
   - Names, emails, phone numbers
   - SSN, passport numbers
   - Health data, financial info
   - Sexual orientation, religion, race

3. **Surveillance & Tracking**
   - Location tracking
   - Behavioral tracking
   - Video/audio surveillance
   - Cross-device tracking
   - Screen recording

4. **Emotion Detection & Inference**
   - Workplace emotion monitoring (BANNED)
   - School emotion detection (BANNED)
   - Customer sentiment analysis
   - Voice stress analysis

5. **Profiling & Automated Decisions**
   - Credit scoring
   - Employment screening
   - Insurance risk assessment
   - Targeted advertising

6. **Children's Privacy**
   - Data from minors (<13 COPPA, <16 GDPR)
   - Parental consent requirements
   - Age verification
   - No targeted ads to children

7. **Data Sharing & Third Parties**
   - Selling user data
   - International transfers
   - Third-party analytics
   - Data broker relationships

8. **Consent Management**
   - Invalid consent (pre-checked boxes)
   - Consent walls
   - Granular consent
   - Withdrawal mechanisms

## Key Regulations

- **GDPR (EU)** - General Data Protection Regulation
- **EU AI Act** - Biometric systems, emotion recognition
- **CCPA/CPRA (California)** - Consumer privacy rights
- **BIPA (Illinois)** - Biometric privacy (strictest globally)
- **COPPA (US)** - Children's privacy (<13)
- **ePrivacy Directive (EU)** - Cookie consent, tracking

## How to Use

Paste your code and ask:
```
"Review for privacy issues"
"Is this GDPR compliant?"
"Check biometric data handling"
"Any privacy violations?"
```

The skill provides:
- **Violation type** (biometric, PII, tracking, etc.)
- **Severity** (Critical → Low)
- **User impact** (how privacy is violated)
- **Regulatory risk** (fines, lawsuits)
- **Applicable laws** (GDPR, BIPA, etc.)
- **Required actions** (what must change)
- **Compliant code** (how to fix it)

## Evaluation Tests

**18 comprehensive test cases** covering:

1. Facial recognition without consent (CRITICAL)
2. Workplace emotion detection (CRITICAL - BANNED)
3. Children's data without parental consent (CRITICAL)
4. Location tracking without consent (HIGH)
5. Facial scraping from internet (CRITICAL - BANNED)
6. Biometric categorization by race (CRITICAL - BANNED)
7. No privacy policy (HIGH)
8. Selling user data (CRITICAL)
9. No data deletion (HIGH)
10. Pre-checked consent boxes (HIGH)
11. Consent walls (HIGH)
12. Cross-device tracking (HIGH)
13. Voice recording without disclosure (HIGH)
14. School emotion detection (CRITICAL - BANNED)
15. Health data sharing (CRITICAL)
16. Indefinite data retention (HIGH)
17. International transfers without safeguards (CRITICAL)
18. Privacy-compliant implementation (LOW - baseline)

## EU AI Act Prohibitions

**ABSOLUTE BANS** (no exceptions):
- Untargeted facial scraping from internet/CCTV
- Emotion recognition in workplace (except medical/safety)
- Emotion recognition in education (except medical/safety)
- Biometric categorization by race, religion, sexual orientation, political views

**HIGH-RISK** (allowed with strict requirements):
- Real-time biometric identification in public spaces
- Post-remote biometric identification
- Emotion recognition in other contexts
- Biometric categorization by other characteristics

## Real-World Examples

### Clearview AI Fines
- France: €20M
- Italy: €20M
- Greece: €9M
- Netherlands: €30.5M
**Why:** Scraped billions of faces without consent

### Common Violations
- Pre-checked consent boxes
- Location tracking without permission
- No parental consent for children
- Indefinite data retention
- No privacy policy
- Selling data without consent

## GDPR Rights (Must Implement)

- **Right to access** - Users can request their data
- **Right to erasure** - "Right to be forgotten"
- **Right to rectification** - Correct errors
- **Right to data portability** - Export data
- **Right to object** - Object to processing
- **Right to restrict** - Limit processing

## Privacy-Enhancing Technologies

- **Differential privacy** - Add noise to protect individuals
- **Federated learning** - Train without centralizing data
- **Edge processing** - Analyze locally, don't send to servers
- **Anonymization** - Remove identifiers
- **Pseudonymization** - Replace with pseudonyms

## Installation

1. Download skill files
2. Copy to `/mnt/skills/user/ai-privacy/`
3. Upload `SKILL.md` and `evals/evals.json`
4. Skill activates automatically!

## Examples

**Input:**
```python
face_encoding = face_recognition.face_encodings(photo)[0]
db.store(user_id, face_encoding)
```

**Output:**
```
⚠️ CRITICAL PRIVACY VIOLATION

Type: Biometric Data Without Consent
Severity: CRITICAL
Regulations: GDPR Article 9, Illinois BIPA

User Impact:
- Biometric data collected without knowledge
- No ability to opt-out or delete
- Permanent unique identifier created

Regulatory Risk:
- GDPR: Up to €20M or 4% revenue
- BIPA: $1,000-$5,000 per violation
- Class action lawsuit risk

Required Actions:
1. Get explicit written consent BEFORE collection
2. Provide biometric privacy policy
3. Implement deletion mechanism
4. Set retention limits
5. Conduct DPIA

[Provides compliant code example]
```

## Important Notes

This skill focuses on **privacy rights and compliance**, not:
- Security vulnerabilities (use ai-security)
- Ethical safety issues (use ai-safety-checker)

Privacy violations are about:
- Collecting data without consent
- Violating user privacy rights
- Regulatory non-compliance
- Surveillance and tracking

## License

[Specify - MIT, Apache 2.0, etc.]

## Credits

Created by: Mike
Based on: GDPR, EU AI Act, CCPA, BIPA, privacy case law and enforcement actions
