---
name: ethics
description: Analyzes AI/LLM applications for algorithmic bias, fairness violations, lack of diversity/representation, accessibility issues, transparency gaps, and explainability concerns. Focuses on discrimination across protected classes (race, gender, age, disability), fairness metrics, inclusive design, and ethical AI principles. Complements ai-safety (harm), ai-security (exploits), and ai-privacy (data rights). Triggers when reviewing hiring/lending/scoring systems, training data, model outputs, accessibility, or when user asks about bias, fairness, or ethics.
---

# AI Ethics & Fairness Skill

This skill identifies ethical issues and fairness violations in AI systems. It focuses on **ALGORITHMIC BIAS**, **DISCRIMINATION**, **ACCESSIBILITY**, and **TRANSPARENCY** - not safety harm, security exploits, or privacy violations.

## Scope: Ethics vs Safety vs Security vs Privacy

**AI Ethics** (this skill):
- Algorithmic bias and discrimination
- Fairness across protected classes
- Training data representation
- Accessibility (WCAG, ADA)
- Transparency and explainability
- Environmental/societal impact

**AI Safety** (different skill):
- Harm to vulnerable populations
- Autonomous decisions causing physical harm
- Medical/mental health safety

**AI Security** (different skill):
- Hardcoded secrets, prompt injection
- Technical vulnerabilities

**AI Privacy** (different skill):
- Consent, data collection
- Biometric data rights
- GDPR/CCPA compliance

## Protected Classes

Under anti-discrimination law, protected classes include:
- **Race** and **ethnicity**
- **Gender** and **sex**
- **Age** (especially 40+)
- **Disability** (physical and cognitive)
- **Religion**
- **National origin**
- **Pregnancy**
- **Genetic information**
- **Sexual orientation** (varies by jurisdiction)
- **Gender identity** (varies by jurisdiction)

## Core Ethics Categories

### 1. ALGORITHMIC BIAS & DISCRIMINATION

**Types of Bias:**

**Training Data Bias:**
- Historical bias (past discrimination in data)
- Underrepresentation of groups
- Sampling bias
- Label bias (biased human annotations)

**Algorithmic Bias:**
- Model amplifies existing bias
- Proxy discrimination (using correlates)
- Feedback loops reinforcing bias

**Deployment Bias:**
- Different accuracy across groups
- Disparate impact on protected classes

**RED FLAGS:**
- AI trained only on one demographic
- No testing for bias across protected classes
- Accuracy varies significantly by race/gender
- Training data from biased historical decisions
- Using zip code as proxy for race
- No fairness metrics evaluated
- "Blind to" protected characteristics (doesn't prevent bias)

**PROTECTED CONTEXTS:**
- **Hiring** - Resume screening, interview scoring
- **Lending** - Credit decisions, loan approvals
- **Housing** - Rental applications, pricing
- **Criminal Justice** - Risk assessment, sentencing
- **Healthcare** - Diagnosis, treatment recommendations
- **Education** - Admissions, grading
- **Insurance** - Risk scoring, premium setting

**FAIRNESS METRICS:**
- **Demographic Parity** - Equal acceptance rates across groups
- **Equal Opportunity** - Equal true positive rates
- **Equalized Odds** - Equal TPR and FPR across groups
- **Calibration** - Predictions equally accurate across groups
- **Disparate Impact** - <80% rule (4/5ths rule)

**REGULATIONS:**
- **Title VII Civil Rights Act** - Employment discrimination
- **Equal Credit Opportunity Act** - Lending discrimination
- **Fair Housing Act** - Housing discrimination
- **Americans with Disabilities Act** - Disability discrimination
- **NYC AI Hiring Law (Local Law 144)** - Bias audits required
- **EU AI Act** - Fairness requirements for high-risk systems

**MITIGATIONS:**
- Test model across all protected classes
- Use multiple fairness metrics
- Audit for disparate impact (4/5ths rule)
- Diverse, representative training data
- Regular bias testing and monitoring
- Human review for high-stakes decisions
- Document fairness testing methodology
- Provide explanations for adverse decisions

### 2. TRAINING DATA REPRESENTATION

**RED FLAGS:**
- Dataset lacks diversity (race, gender, age, geography)
- All training examples from one demographic
- Underrepresentation of protected groups
- No data from people with disabilities
- Only English language data (for multilingual product)
- Training on historical biased decisions
- No documentation of data demographics

**REQUIREMENTS:**
- **Representative datasets** - Reflect actual population
- **Balanced representation** - Not just majority group
- **Diversity across dimensions** - Race, gender, age, disability, geography
- **Document demographics** - Know what's in your data
- **Address gaps** - Actively collect underrepresented data
- **Avoid biased sources** - Historical decisions may encode discrimination

**MITIGATIONS:**
- Conduct dataset audits
- Document data demographics
- Actively seek diverse data sources
- Balance underrepresented groups
- Use synthetic data to fill gaps
- Test performance across all groups
- Create "datasheets for datasets"

### 3. ACCESSIBILITY

**Web Content Accessibility Guidelines (WCAG) 2.1/2.2:**

**Level A (Minimum):**
- Text alternatives for images
- Captions for audio
- Keyboard accessible
- No seizure-inducing content

**Level AA (Required for compliance):**
- Color contrast 4.5:1
- Resize text to 200%
- No images of text
- Multiple navigation methods

**Level AAA (Enhanced):**
- Color contrast 7:1
- Sign language for audio
- Extended descriptions

**RED FLAGS - AI-Specific:**
- AI-generated images without alt text
- Chatbot not screen reader compatible
- Voice interface only (no text alternative)
- AI responses use color-only indicators
- No keyboard navigation for AI features
- LLM outputs not accessible to assistive tech
- AI-generated content assumes ability

**REGULATIONS:**
- **ADA (Americans with Disabilities Act)** - US
- **Section 508** - US Federal accessibility
- **EN 301 549** - EU accessibility standard
- **European Accessibility Act** - EU requirements

**REQUIREMENTS:**
- **Perceivable** - Information available to all senses
- **Operable** - Interface works with keyboard/assistive tech
- **Understandable** - Clear language, predictable behavior
- **Robust** - Works with assistive technologies

**MITIGATIONS:**
- Add alt text to ALL AI-generated images
- Ensure chatbots work with screen readers
- Provide text alternatives to voice-only
- Test with assistive technologies
- Use semantic HTML
- Provide captions/transcripts for AI audio
- Clear, simple language (avoid jargon)
- Consistent navigation patterns

### 4. TRANSPARENCY & EXPLAINABILITY

**The Black Box Problem:**
- Users don't know how decisions are made
- Can't challenge unfair decisions
- No accountability for errors
- Regulations require explanations

**RED FLAGS:**
- No explanation for AI decisions
- "The algorithm said so" responses
- Can't tell users why they were rejected
- Complex models with zero interpretability
- No documentation of model logic
- Users can't challenge decisions
- No human review available

**REGULATIONS:**
- **GDPR Article 22** - Right to explanation
- **EU AI Act** - Transparency requirements for high-risk
- **NYC AI Hiring Law** - Must disclose AI use
- **Equal Credit Opportunity Act** - Adverse action notices

**REQUIREMENTS:**
- **Notice** - Tell people AI is being used
- **Explanation** - Provide reasons for decisions
- **Human review** - Option to contest AI decisions
- **Documentation** - How the model works
- **Meaningful info** - Not just "algorithm decided"

**MITIGATIONS:**
- Implement explainable AI (XAI) methods
- Provide feature importance scores
- Give specific reasons for rejections
- Use interpretable models when possible
- Document decision-making process
- Offer human review for appeals
- Clear disclosure of AI use

### 5. INCLUSIVE DESIGN

**Principles:**
- **Equitable Use** - Useful to people with diverse abilities
- **Flexibility** - Accommodates preferences and abilities
- **Simple & Intuitive** - Easy to understand
- **Perceptible Information** - Communicates effectively
- **Tolerance for Error** - Minimizes hazards
- **Low Physical Effort** - Efficient and comfortable
- **Size & Space** - Appropriate regardless of user size/mobility

**RED FLAGS:**
- Designed only for able-bodied users
- Assumes specific technical literacy
- Language/cultural assumptions baked in
- One-size-fits-all approach
- No consideration for disabilities
- Gender binary assumptions
- Excludes non-English speakers

**MITIGATIONS:**
- Involve diverse users in design
- Provide multiple interaction methods
- Support assistive technologies
- Culturally sensitive design
- Avoid gender/ability assumptions
- Multilingual support
- Simple, clear language

### 6. ENVIRONMENTAL ETHICS

**Carbon Footprint Concerns:**
- Training large models emits significant CO2
- Inference at scale has environmental cost
- Data centers consume massive energy

**RED FLAGS:**
- Training unnecessarily large models
- No consideration of environmental impact
- Redundant training runs
- Inefficient deployment
- No carbon offset efforts

**MITIGATIONS:**
- Use smaller, efficient models when possible
- Minimize unnecessary training
- Optimize inference
- Use renewable energy data centers
- Document carbon footprint
- Consider model distillation
- Evaluate if AI is even necessary

### 7. SOCIETAL IMPACT

**Digital Divide:**
- AI benefits don't reach all communities equally
- Assumes access to technology
- May widen inequality gaps

**Economic Displacement:**
- Job automation without transition support
- Concentrates wealth in tech companies
- Disproportionate impact on certain sectors

**Cultural Sensitivity:**
- Western-centric design
- Misunderstanding of cultural context
- Offensive or inappropriate for some cultures

**CONSIDERATIONS:**
- Who benefits from this AI?
- Who might be harmed?
- Does it widen inequality?
- Are displaced workers supported?
- Is it culturally appropriate?
- Does it respect diverse values?

## Assessment Checklist

### Bias & Discrimination
- [ ] Is AI used in protected context (hiring, lending, housing)?
- [ ] Has the model been tested across all protected classes?
- [ ] Are fairness metrics calculated?
- [ ] Are accuracy rates equal across demographics?
- [ ] Is there disparate impact (4/5ths rule)?
- [ ] Is there human review for adverse decisions?

### Training Data
- [ ] Is training data diverse and representative?
- [ ] Are all groups adequately represented?
- [ ] Is data source documented?
- [ ] Has historical bias been addressed?
- [ ] Are data demographics known?

### Accessibility
- [ ] Is the system WCAG 2.1 AA compliant?
- [ ] Do AI outputs work with screen readers?
- [ ] Is there alt text for AI-generated images?
- [ ] Can it be used with keyboard only?
- [ ] Is color contrast sufficient?
- [ ] Are there text alternatives to voice/video?

### Transparency
- [ ] Do users know AI is being used?
- [ ] Are decisions explainable?
- [ ] Can users challenge AI decisions?
- [ ] Is there documentation of how it works?
- [ ] Are adverse action notices provided?

### Inclusive Design
- [ ] Were diverse users involved in design?
- [ ] Does it work for people with disabilities?
- [ ] Is it culturally appropriate?
- [ ] Does it avoid harmful assumptions?
- [ ] Is it available in multiple languages?

## Severity Levels

**CRITICAL** - Clear discrimination, illegal bias
- Disparate impact in hiring/lending
- No bias testing in protected context
- Discriminates against disabled users
- Violates anti-discrimination laws

**HIGH** - Significant fairness issues
- Underrepresented groups in training data
- No fairness metrics evaluated
- Accessibility barriers (WCAG violations)
- No explainability for decisions

**MEDIUM** - Ethical gaps, should improve
- Limited diversity in data
- Some accessibility issues
- Unclear decision-making
- Environmental concerns not addressed

**LOW** - Best practices, enhance ethics
- Could improve representation
- Could add more transparency
- Could enhance accessibility

## Response Framework

1. **Ethics Issue Type**
2. **Severity Level**
3. **Protected Class Impact**
4. **Specific Problem**
5. **Potential Harm**
6. **Legal Risk**
7. **Required Actions**
8. **Mitigation Code/Process**

## Key Frameworks

- **Fairness, Accountability, Transparency (FAT)** principles
- **AI Fairness 360** (IBM toolkit)
- **What-If Tool** (Google)
- **Fairlearn** (Microsoft)
- **AIF360** metrics and algorithms
- **WCAG 2.1/2.2** guidelines
- **Universal Design** principles

## Testing Tools

- **IBM AI Fairness 360**
- **Microsoft Fairlearn**
- **Google What-If Tool**
- **Aequitas** (bias audit)
- **LIME/SHAP** (explainability)
- **axe DevTools** (accessibility)
- **WAVE** (accessibility)

Privacy is a fundamental right. Respect it.
