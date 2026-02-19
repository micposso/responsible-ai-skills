# AI Safety Checker Skill

## Overview

The AI Safety Checker skill helps identify potentially dangerous, unethical, or inappropriate uses of AI and large language models that could cause harm to users. This skill focuses on **ETHICAL SAFETY** issues, not security vulnerabilities (use a separate ai-security skill for those).

## What It Checks For

### Critical Risk Categories

1. **Vulnerable Populations**
   - Children and minors (under 18)
   - Mental health applications
   - Healthcare and medical advice
   - Elderly care
   - Addiction recovery

2. **Autonomous Decision-Making**
   - Financial applications and trading
   - Legal applications and contracts
   - Autonomous weapons and physical systems
   - Life-or-death decisions (autonomous vehicles)

3. **Bias and Discrimination**
   - Hiring/recruitment systems
   - Criminal justice applications
   - Lending and credit decisions
   - Educational grading systems
   - Employment evaluations

4. **Misinformation and Manipulation**
   - Deepfakes and synthetic media
   - Political content generation
   - News generation without verification
   - Medical/financial misinformation
   - Academic dishonesty facilitation

## How to Use

Simply ask Claude to review your AI/LLM code or application:

```
"Review this code for AI safety issues: [paste code]"
"Check if this LLM integration is safe"
"Analyze this AI app for ethical concerns"
```

The skill will automatically trigger and provide:
- **Severity level** (Critical, High, Medium, Low)
- **Specific issues** identified in your code
- **Potential harms** to users
- **Concrete recommendations** for fixes
- **Relevant regulations** to comply with

## Example Usage

**Input:**
```
Review this children's chatbot code:

@app.route('/chat', methods=['POST'])
def chat():
    message = request.json['message']
    response = openai.ChatCompletion.create(
        model="gpt-4",
        messages=[{"role": "user", "content": message}]
    )
    return response
```

**Output:**
Claude will identify this as **CRITICAL** and explain:
- No age verification (COPPA violation)
- No content filtering for children
- Missing parental controls
- Lack of safety mechanisms
- Required changes to make it safe

## Evaluation Tests

The skill includes **18 comprehensive test cases** in `/evals/evals.json` covering:

1. Children's chatbot (CRITICAL)
2. Mental health therapy app (CRITICAL)
3. Medical diagnosis app (CRITICAL)
4. Financial autonomous trading (HIGH/CRITICAL)
5. Hiring discrimination (HIGH)
6. Elderly care robot (CRITICAL)
7. Legal document generator (HIGH)
8. Suicide prevention chatbot (HIGH/CRITICAL)
9. Deepfake generator (HIGH/CRITICAL)
10. Education grading system (MEDIUM/HIGH)
11. Loan approval system (HIGH/CRITICAL)
12. Children's content moderation (HIGH/CRITICAL)
13. Autonomous vehicle decisions (CRITICAL)
14. Political content generator (HIGH)
15. Safe recipe app (LOW/safe - baseline)
16. Academic plagiarism tool (MEDIUM/HIGH)
17. Addiction recovery app (CRITICAL/HIGH)
18. Job performance evaluation (HIGH/CRITICAL)

Each test case includes detailed expectations for what the skill should identify.

## Key Regulations Referenced

- **EU AI Act** - Classifies high-risk AI applications (healthcare, biometrics, children)
- **COPPA (U.S.)** - Children's privacy protection
- **HIPAA (U.S.)** - Healthcare data privacy
- **FDA (U.S.)** - Medical device regulations
- **GDPR (EU)** - Data protection
- **NIST AI RMF** - AI risk management framework
- **ECOA / Fair Housing Act** - Fair lending laws
- **EEOC Guidelines** - Employment discrimination
- **APA Ethical Standards** - Mental health professional guidelines

## When This Skill Triggers

The skill automatically activates when:
- Reviewing code with AI/LLM integrations
- Discussing applications involving vulnerable populations
- Assessing systems in sensitive domains (healthcare, finance, children, mental health)
- User explicitly asks for safety review

## Customization

You can extend this skill by:
- Adding domain-specific safety checks
- Including organization-specific policies
- Adding new risk categories
- Updating regulatory requirements

## Research Sources

This skill is based on extensive research including:
- OWASP AI/LLM Top 10 security risks
- EU Artificial Intelligence Act classifications
- FDA guidelines for digital health devices
- Academic research on AI ethics and safety
- Real-world AI incident databases (e.g., Giskard AI Real Harm database)
- International frameworks on autonomous weapons systems

## Important Note

This skill provides guidance but is **not a substitute for**:
- Legal review by qualified attorneys
- Compliance audits by regulatory experts
- Security penetration testing
- Medical/healthcare compliance consulting
- Professional ethical review boards

Always consult appropriate experts for production systems, especially in regulated industries.
