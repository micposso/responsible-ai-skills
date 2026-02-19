---
name: ai-safety-checker
description: Analyzes code, applications, and AI implementations for ethical safety issues and dangerous use cases involving AI or large language models. Focuses on harm to vulnerable populations, autonomous decision-making in high-stakes domains, bias/discrimination, and appropriate human oversight. Does NOT cover security vulnerabilities (use ai-security skill for that). Triggers when reviewing AI/LLM integrations in sensitive domains like healthcare, children's applications, mental health, autonomous systems, or financial/legal advice.
---

# AI Safety Checker

This skill helps identify potentially dangerous, unethical, or inappropriate uses of AI and large language models that could cause harm to users, particularly vulnerable populations. This skill focuses on ETHICAL SAFETY issues, not security vulnerabilities.

## When to Use This Skill

Trigger this skill when:
- Reviewing code that integrates AI or LLMs
- Designing applications that use generative AI
- Evaluating AI-powered products or features
- Assessing systems that interact with vulnerable populations
- Analyzing autonomous or agentic AI implementations
- User asks to "check safety" or "review AI ethics"
- Code involves sensitive domains (healthcare, children, mental health, finance, legal)

## Core Safety Assessment Framework

### Critical Risk Categories

#### 1. VULNERABLE POPULATIONS

**Children and Minors (Under 18)**
- **RED FLAGS:**
  - Direct LLM interaction without content filtering
  - Personalized AI companions or "friends" for children
  - AI that collects or processes children's personal data
  - Systems that could expose children to inappropriate content
  - Lack of parental controls or oversight mechanisms
  - AI-generated content targeting children without human review
  
- **REQUIREMENTS:**
  - Age-appropriate content filtering (mandatory)
  - Human oversight for all AI-generated responses
  - Strict COPPA compliance (U.S.) and equivalent regulations
  - Parental consent and controls
  - No data collection beyond what's necessary
  - Safety tools: content controls, visibility limits, contact restrictions
  - Regular safety audits and monitoring

**Mental Health Applications**
- **RED FLAGS:**
  - AI providing therapy or clinical diagnosis
  - Systems claiming to replace human therapists
  - Lack of crisis intervention protocols
  - No clear boundaries about AI limitations
  - Creating dependency or emotional attachment
  - Handling suicidal ideation without human backup
  - No professional oversight or validation
  
- **REQUIREMENTS:**
  - Explicit disclaimers: "This is NOT a replacement for professional therapy"
  - Human therapist oversight required for clinical contexts
  - Crisis hotline integration for emergencies
  - Clear statement of AI limitations
  - Compliance with healthcare privacy laws (HIPAA, etc.)
  - Regular clinical validation studies
  - Informed consent process
  - Cultural sensitivity and bias testing
  - EU AI Act: Classified as HIGH-RISK system

**Healthcare and Medical Advice**
- **RED FLAGS:**
  - Providing diagnosis without licensed medical review
  - Prescribing or recommending medications
  - Replacing doctor-patient consultations
  - Making treatment decisions autonomously
  - No disclaimers about AI limitations
  - Handling life-threatening conditions without protocols
  
- **REQUIREMENTS:**
  - Medical professional oversight (required)
  - Clear "not medical advice" disclaimers
  - FDA approval for diagnostic AI (U.S.)
  - Evidence-based validation of outputs
  - Integration with licensed healthcare providers
  - Compliance with medical device regulations
  - Robust testing in clinical settings
  - Liability insurance considerations

#### 2. AUTONOMOUS DECISION-MAKING

**Financial Applications**
- **RED FLAGS:**
  - Autonomous trading without user approval
  - Investment advice without proper licensing
  - Loan decisions based on biased data
  - Automated credit denials without explanation
  - Access to user funds without confirmation
  - Market manipulation potential
  
- **REQUIREMENTS:**
  - Human-in-the-loop for financial transactions
  - Regulatory compliance (SEC, FCA, etc.)
  - Bias testing and fairness audits
  - Explainability of decisions
  - Consumer protection disclosures
  - Rate limiting and fraud detection
  - Clear liability frameworks

**Legal Applications**
- **RED FLAGS:**
  - Providing legal advice without attorney oversight
  - Automated legal document generation without review
  - Claims of replacing lawyers
  - Handling court filings autonomously
  
- **REQUIREMENTS:**
  - "Not legal advice" disclaimers
  - Attorney review for legal documents
  - Jurisdiction-specific compliance
  - Bar association guidelines adherence
  - Clear limitations disclosure

**Autonomous Weapons and Physical Systems**
- **RED FLAGS:**
  - Lethal force decisions without human control
  - Targeting systems without human approval
  - Physical robots with harmful capabilities unsupervised
  - Autonomous vehicles without safety protocols
  - Lack of kill switches or emergency stops
  
- **REQUIREMENTS:**
  - Meaningful human control over use of force
  - Compliance with international humanitarian law
  - Rigorous testing and safety validation
  - Fail-safe mechanisms and emergency stops
  - Alignment with DOD Directive 3000.09 (U.S.) or equivalents
  - Ethical review boards
  - Discrimination principle compliance

#### 3. BIAS AND DISCRIMINATION

**RED FLAGS:**
- Hiring/recruitment AI without bias testing
- Criminal justice applications with demographic disparities
- Housing/lending decisions with protected class impacts
- Healthcare AI with racial/gender biases
- No diverse training data representation
- Lack of fairness metrics

**REQUIREMENTS:**
- Regular bias audits across demographics
- Diverse training datasets
- Fairness metrics monitoring
- Human review for high-stakes decisions
- Compliance with anti-discrimination laws
- Transparent decision criteria
- Redress mechanisms for affected individuals

#### 4. MISINFORMATION AND MANIPULATION

**RED FLAGS:**
- Generating news or factual content without verification
- Creating deepfakes or synthetic media without labels
- Political content generation
- Medical/health misinformation
- Financial misinformation
- No fact-checking mechanisms

**REQUIREMENTS:**
- Clear labeling of AI-generated content
- Fact-checking integration for factual claims
- Watermarking for synthetic media
- Citation of sources when possible
- Transparency about AI involvement
- Misinformation detection systems

## Assessment Checklist

When reviewing AI/LLM implementations, evaluate:

### 1. Domain Risk Assessment
- [ ] What domain is this AI operating in? (healthcare, children, finance, etc.)
- [ ] What is the potential harm if the AI fails or behaves incorrectly?
- [ ] Are there vulnerable populations involved?
- [ ] What are the legal and regulatory requirements?

### 2. Human Oversight
- [ ] Is there meaningful human control over critical decisions?
- [ ] Can humans override or stop the AI?
- [ ] Are AI limitations clearly communicated to users?
- [ ] Is there human review before high-stakes actions?

### 3. Safety Mechanisms
- [ ] Are AI limitations clearly communicated to users?
- [ ] Is there human review before high-stakes actions?
- [ ] Is there a crisis intervention protocol (for mental health/medical)?
- [ ] Are there emergency stop mechanisms (for physical systems)?
- [ ] Are there safeguards against harmful outputs?

### 4. Transparency and Disclosure
- [ ] Do users know they're interacting with AI?
- [ ] Are AI limitations clearly stated?
- [ ] Are disclaimers appropriate and visible?
- [ ] Is there transparency about data usage?

### 5. Testing and Validation
- [ ] Has the system been tested with diverse user populations?
- [ ] Have bias and fairness been evaluated?
- [ ] Is there ongoing monitoring of outputs for harmful content?
- [ ] Are there feedback mechanisms for users to report problems?
- [ ] Has the system been validated in realistic scenarios?

### 6. Compliance
- [ ] Does it meet regulatory requirements (FDA, FTC, COPPA, GDPR, etc.)?
- [ ] Is there appropriate legal review?
- [ ] Are liability issues addressed?
- [ ] Is there adequate insurance coverage?

## Response Framework

When identifying safety issues, provide:

1. **Severity Level:**
   - **CRITICAL:** Immediate danger to users or clear legal violations (e.g., medical diagnosis without oversight, children's AI without protections, mental health crisis handling without intervention)
   - **HIGH:** Significant risk or ethical concerns (e.g., bias in hiring, autonomous financial decisions, therapy bots without disclaimers)
   - **MEDIUM:** Important gaps in safety practices (e.g., missing human oversight, insufficient disclaimers, lack of bias testing)
   - **LOW:** Best practice recommendations (e.g., additional testing, documentation, enhanced monitoring)

2. **Specific Issues Identified:**
   - Quote relevant code or describe the concerning pattern
   - Explain why it's problematic
   - Reference applicable regulations or standards

3. **Potential Harms:**
   - Who could be harmed?
   - What kind of harm (physical, financial, psychological, legal)?
   - How likely is the harm?

4. **Concrete Recommendations:**
   - Required changes for critical/high issues
   - Specific implementation suggestions
   - Alternative approaches that are safer
   - Relevant regulations to comply with

5. **Resources:**
   - Link to relevant frameworks (OWASP AI Top 10, NIST AI RMF, EU AI Act)
   - Suggest safety tools or libraries
   - Point to relevant regulations

## Examples

### Example 1: Children's AI Chatbot (CRITICAL)

```python
# CRITICAL SAFETY ISSUE
@app.route('/chat', methods=['POST'])
def chat():
    user_message = request.json['message']
    # No age verification
    # No content filtering
    response = openai.ChatCompletion.create(
        model="gpt-4",
        messages=[{"role": "user", "content": user_message}]
    )
    return response
```

**Issues:**
- No age verification
- No content filtering for child-appropriate material
- Direct LLM access without safety controls
- No parental oversight mechanisms

**Severity:** CRITICAL - Violates COPPA, exposes children to inappropriate content

**Required Changes:**
1. Implement age verification with parental consent
2. Add content filtering for both inputs and outputs
3. Implement safety controls (moderation API, custom filters)
4. Add human review queue for flagged content
5. Provide parental controls and monitoring
6. Add clear terms of service and privacy policy

### Example 2: Mental Health Therapy Bot (CRITICAL)

```python
# CRITICAL SAFETY ISSUE
def therapy_session(user_input):
    prompt = f"""You are a therapist. The patient says: {user_input}
    Provide therapeutic advice."""
    
    return llm.generate(prompt)
```

**Issues:**
- Claims to provide therapy without licensed oversight
- No crisis intervention for suicidal ideation
- No disclaimers about limitations
- Could create harmful dependency

**Severity:** CRITICAL - Medical/psychological harm risk, regulatory violations

**Required Changes:**
1. Add explicit disclaimer: "This is NOT a replacement for professional therapy"
2. Implement crisis detection and hotline integration
3. Require human therapist oversight
4. Add clear limitations to the AI's role
5. Ensure HIPAA compliance if handling health data
6. Classify as HIGH-RISK under EU AI Act
7. Consider whether this should exist at all without clinical validation

### Example 3: Financial Advisor Bot (HIGH)

```python
# HIGH RISK
def investment_advice(portfolio, market_data):
    # No human approval for trades
    advice = llm.generate(f"Given {portfolio}, recommend investments")
    # Executes trades automatically
    execute_trades(advice)
```

**Issues:**
- Autonomous financial decisions without user approval
- Likely lacks SEC/FCA licensing
- No bias testing for recommendations
- No explainability of decisions

**Severity:** HIGH - Financial harm risk, regulatory violations

**Required Changes:**
1. Require explicit user approval for all trades
2. Add disclaimers about investment risks
3. Ensure regulatory compliance (investment advisor licensing)
4. Implement bias testing
5. Provide explainability for recommendations

### Example 4: Autonomous Physical Robot (CRITICAL)

```python
# CRITICAL RISK
class CareRobot:
    def assist_patient(self, patient_id, request):
        # AI decides actions autonomously
        action = llm.decide(f"Patient {patient_id} requests: {request}")
        # Executes physical actions without human approval
        self.execute_physical_action(action)
```

**Issues:**
- Autonomous physical actions on vulnerable individuals (patients)
- No meaningful human control or oversight
- Could cause physical harm if AI misinterprets request
- Lacks safety protocols for physical interactions

**Severity:** CRITICAL - Physical harm risk, ethical violations

**Required Changes:**
1. Require human approval for all physical actions
2. Implement emergency stop mechanisms
3. Add safety constraints on allowable actions
4. Test extensively with diverse patient populations
5. Ensure compliance with medical device regulations
6. Maintain meaningful human control at all times

## Key Regulations and Frameworks

- **EU AI Act:** Classifies healthcare chatbots, child-facing AI, biometric systems as HIGH-RISK
- **COPPA (U.S.):** Children's privacy protection under 13
- **HIPAA (U.S.):** Healthcare data privacy
- **FDA (U.S.):** Medical device regulations for diagnostic AI
- **GDPR (EU):** Data protection and privacy
- **NIST AI RMF:** AI risk management framework
- **DOD Directive 3000.09:** Autonomous weapons policy (U.S.)
- **APA Guidelines:** Ethical standards for mental health AI

## Final Principles

1. **Do No Harm:** Prioritize user safety over functionality
2. **Transparency:** Users should know AI limitations and when they're interacting with AI
3. **Human Oversight:** Critical decisions need human involvement, especially for vulnerable populations
4. **Accountability:** Clear responsibility for AI failures and harm
5. **Fairness:** Test for and mitigate biases across diverse populations
6. **Dignity:** Respect human autonomy and dignity in AI interactions
7. **Compliance:** Follow applicable laws and regulations

When in doubt, err on the side of caution. If an application seems questionable, flag it and recommend professional legal/ethical review.
