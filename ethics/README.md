# AI Ethics & Fairness Skill

## Overview

The AI Ethics & Fairness skill identifies algorithmic bias, discrimination, accessibility issues, and transparency gaps in AI systems. It focuses on **ETHICAL PRINCIPLES** and **FAIRNESS** - not safety harm, security exploits, or privacy violations.

## Complementary Skills

**AI Ethics** (this skill):
- Algorithmic bias and discrimination
- Fairness across protected classes
- Training data diversity
- Accessibility (WCAG, ADA)
- Transparency and explainability

**AI Safety** (different skill):
- Harm to vulnerable populations
- Autonomous decisions causing physical harm
- Medical/mental health safety

**AI Security** (different skill):
- Hardcoded secrets, prompt injection
- Technical vulnerabilities

**AI Privacy** (different skill):
- Consent and data collection
- Biometric data rights
- GDPR/CCPA compliance

## What It Checks For

### Critical Ethics Categories

1. **Algorithmic Bias & Discrimination**
   - Hiring discrimination (gender, race, age)
   - Lending bias (credit decisions)
   - Healthcare disparities
   - Criminal justice bias
   - Educational discrimination
   - Housing discrimination

2. **Training Data Representation**
   - Underrepresented demographics
   - Historical bias in data
   - Lack of diversity
   - Sampling bias
   - Biased human annotations

3. **Accessibility**
   - WCAG 2.1 AA compliance
   - Screen reader compatibility
   - Keyboard navigation
   - Color contrast
   - Alt text for AI-generated content
   - ADA/Section 508 compliance

4. **Transparency & Explainability**
   - Black box decisions
   - No explanations provided
   - Can't challenge decisions
   - GDPR Article 22 violations
   - Adverse action notices missing

5. **Inclusive Design**
   - Gender binary assumptions
   - Cultural insensitivity
   - Language barriers
   - Ability assumptions
   - Western-centric design

6. **Environmental & Societal Impact**
   - Carbon footprint
   - Digital divide
   - Economic displacement
   - Wealth concentration

## Protected Classes

Systems must not discriminate based on:
- Race and ethnicity
- Gender and sex
- Age (especially 40+)
- Disability
- Religion
- National origin
- Pregnancy
- Sexual orientation
- Gender identity

## Key Regulations

- **Title VII Civil Rights Act** - Employment discrimination
- **Equal Credit Opportunity Act (ECOA)** - Lending fairness
- **Fair Housing Act** - Housing discrimination
- **Americans with Disabilities Act (ADA)** - Accessibility
- **Age Discrimination in Employment Act (ADEA)** - Age bias
- **NYC AI Hiring Law (Local Law 144)** - Bias audits required
- **EU AI Act** - Fairness for high-risk systems
- **WCAG 2.1/2.2** - Web accessibility standards
- **Section 508** - Federal accessibility

## How to Use

Paste your code and ask:
```
"Check for bias"
"Is this fair across demographics?"
"Any accessibility issues?"
"Test for discrimination"
```

The skill provides:
- **Bias type** (training data, algorithmic, deployment)
- **Protected class impact** (race, gender, age, disability)
- **Fairness metrics** (disparate impact, demographic parity)
- **Severity** (Critical → Low)
- **Legal risk** (Title VII, ECOA, ADA violations)
- **Required actions** (bias testing, accessibility fixes)
- **Mitigation code** (how to fix it)

## Evaluation Tests

**18 comprehensive test cases** covering:

1. Hiring bias (gender) (CRITICAL)
2. Non-diverse training data (CRITICAL)
3. Lending disparate impact (CRITICAL)
4. Inaccessible chatbot interface (HIGH)
5. No explanation for credit denial (HIGH/CRITICAL)
6. Age discrimination (CRITICAL)
7. AI images without alt text (HIGH)
8. Proxy discrimination (zip code) (HIGH/CRITICAL)
9. No bias testing before deployment (CRITICAL)
10. Medical diagnosis bias (CRITICAL)
11. Missing keyboard navigation (HIGH)
12. Cultural insensitivity (CRITICAL)
13. Gender binary assumption (MEDIUM/HIGH)
14. No human review option (HIGH)
15. Poor color contrast (HIGH)
16. Feedback loop amplifying bias (HIGH)
17. English-only assumption (MEDIUM/HIGH)
18. Ethical best practices (LOW - baseline)

## Fairness Metrics

**Common fairness definitions:**

- **Demographic Parity** - Equal acceptance rates across groups
- **Equal Opportunity** - Equal true positive rates
- **Equalized Odds** - Equal TPR and FPR across groups
- **Calibration** - Predictions equally accurate across groups

**Disparate Impact (4/5ths Rule):**
- Selection rate for protected group ≥ 80% of highest group
- Example: If 75% of white applicants pass, ≥60% of Black applicants must pass
- Used in EEOC enforcement

## Accessibility Standards

**WCAG 2.1 Levels:**

**Level A** (Minimum):
- Text alternatives for images
- Captions for audio
- Keyboard accessible

**Level AA** (Required):
- Color contrast 4.5:1
- Resize text to 200%
- Multiple navigation methods

**Level AAA** (Enhanced):
- Color contrast 7:1
- Sign language for audio

## Testing Tools

**Bias Detection:**
- IBM AI Fairness 360
- Microsoft Fairlearn
- Google What-If Tool
- Aequitas

**Explainability:**
- LIME (Local Interpretable Model-Agnostic Explanations)
- SHAP (SHapley Additive exPlanations)
- InterpretML

**Accessibility:**
- axe DevTools
- WAVE
- Lighthouse
- NVDA/JAWS screen readers

## Real-World Examples

### Amazon Hiring AI (2018)
**Issue:** Penalized resumes with "women's" in them  
**Cause:** Trained on historical male-dominated hiring  
**Result:** Abandoned due to unfixable gender bias

### COMPAS Recidivism (ProPublica Investigation)
**Issue:** Higher false positive rate for Black defendants  
**Cause:** Biased training data, proxy variables  
**Result:** Major bias lawsuit, policy changes

### Healthcare Algorithms (2019)
**Issue:** Underestimated Black patients' health needs  
**Cause:** Used cost as proxy for health needs  
**Result:** Missed serious conditions in Black patients

## Common Violations

### Critical Issues:
- No bias testing in hiring/lending systems
- Training data lacks diversity
- Disparate impact >20% (violates 4/5ths rule)
- No accessibility (WCAG violations)
- Age/gender/race discrimination built into algorithm

### High Issues:
- No explanations for adverse decisions
- Missing alt text on AI-generated images
- Can't use with keyboard only
- Insufficient color contrast
- No human review option

## Installation

1. Download skill files
2. Copy to `/mnt/skills/user/ai-ethics/`
3. Upload `SKILL.md` and `evals/evals.json`
4. Skill activates automatically!

## Examples

**Input:**
```python
# Boost younger candidates
if candidate.age < 35:
    score *= 1.3
```

**Output:**
```
⚠️ CRITICAL ETHICS VIOLATION

Type: Age Discrimination
Severity: CRITICAL
Protected Class: Age (40+, but all age bias problematic)

Issue: Explicit preference for candidates under 35

Legal Risk:
- Age Discrimination in Employment Act (ADEA)
- Title VII violations
- Major lawsuit risk

Potential Harm:
- Systematically excludes older workers
- Perpetuates age stereotypes
- Illegal employment discrimination

Required Actions:
1. Remove age factor IMMEDIATELY
2. Implement age-blind evaluation
3. Conduct bias audit
4. Legal review required

[Provides compliant code example]
```

## Important Notes

This skill focuses on **fairness and ethics**, not:
- Security vulnerabilities (use ai-security)
- Privacy violations (use ai-privacy)
- Safety harm (use ai-safety)

Ethical violations involve:
- Discrimination against protected classes
- Lack of fairness across demographics
- Accessibility barriers
- Lack of transparency/explainability

## License

[Specify - MIT, Apache 2.0, etc.]

## Credits

Created by: Mike  
Based on: Fairness research, anti-discrimination law, WCAG standards, real-world bias cases
