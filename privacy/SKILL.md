---
name: privacy
description: Analyzes AI/LLM applications for privacy violations, PII misuse, biometric data concerns, surveillance risks, and data protection compliance. Focuses on privacy RIGHTS and consent, not security vulnerabilities. Covers GDPR, CCPA, BIPA, facial recognition, emotion detection, location tracking, and user data collection. Complements ai-security (technical exploits) and ai-safety-checker (ethical harm). Triggers when reviewing code involving personal data, biometrics, cameras, location, or data collection.
---

# AI Privacy Skill

This skill identifies privacy violations and data protection issues in AI and LLM applications. It focuses on **PRIVACY RIGHTS** and user consent, not security exploits (use ai-security for that) or ethical harm (use ai-safety-checker for that).

## Scope: Privacy vs Security vs Safety

**AI Privacy** (this skill):
- Privacy rights violations
- Consent and data collection
- Biometric data misuse
- Surveillance concerns
- Data protection regulations (GDPR, CCPA, BIPA)

**AI Security** (different skill):
- Technical exploits and attacks
- Hardcoded secrets
- Prompt injection
- Data breaches from vulnerabilities

**AI Safety** (different skill):
- Ethical harm to vulnerable populations
- Bias and discrimination
- Autonomous decisions causing harm

## When to Use This Skill

Trigger this skill when:
- Code collects, processes, or stores personal data
- Applications use cameras, microphones, or sensors
- Biometric data (facial recognition, fingerprints, voice) is involved
- Location tracking or geolocation is used
- User profiling or behavioral tracking occurs
- Data is shared with third parties
- User asks about "privacy", "GDPR", "consent", or "data collection"

## Core Privacy Categories

### 1. BIOMETRIC DATA COLLECTION

Biometric data = physical, physiological, or behavioral characteristics used for unique identification.

**Types of Biometric Data:**
- **Facial recognition** - Facial images, facial templates, face geometry
- **Fingerprints** - Fingerprint scans, palm prints
- **Iris/retina** - Eye scans
- **Voice** - Voice prints, speech patterns
- **Gait** - Walking patterns
- **Behavioral** - Typing patterns, mouse movements, signature dynamics

**RED FLAGS:**
- Collecting facial images without explicit consent
- Scraping faces from internet/CCTV (EU AI Act: BANNED)
- Creating biometric databases
- Real-time facial recognition in public spaces (heavily restricted)
- Emotion recognition from faces in workplace/education (EU AI Act: BANNED)
- Biometric categorization by race, religion, sexual orientation (EU AI Act: BANNED)
- No data retention limits for biometric data
- Biometric data shared with third parties
- No option to delete biometric data

**REGULATIONS:**
- **GDPR Article 9** - Special category data, requires explicit consent
- **EU AI Act Article 5** - Prohibits untargeted facial scraping, workplace emotion detection
- **Illinois BIPA** - Strictest biometric law globally, written consent required
- **CCPA** - California residents have rights over biometric data

**REQUIREMENTS:**
- **Explicit written consent** before collection
- **Clear purpose** - what it's used for
- **Data minimization** - collect only what's needed
- **Retention limits** - delete when no longer needed
- **Right to deletion** - users can request removal
- **No function creep** - can't repurpose for new uses
- **Transparency** - users must know it's happening
- **DPIA required** - Data Protection Impact Assessment

**MITIGATIONS:**
- Get explicit, informed, written consent
- Don't scrape biometric data from internet
- Implement retention limits (delete after X days/months)
- Provide clear opt-out mechanisms
- Store encryption keys with user, not centrally
- Use edge processing (analyze locally, don't store)
- Conduct DPIA before deployment
- Check EU AI Act prohibited practices

### 2. PERSONALLY IDENTIFIABLE INFORMATION (PII)

**Types of PII:**
- **Direct identifiers:** Name, email, phone, SSN, passport number
- **Quasi-identifiers:** Age + ZIP code, IP address, device ID
- **Sensitive PII:** Health data, financial info, sexual orientation, religion, race

**RED FLAGS:**
- Collecting PII without clear purpose
- No privacy policy or consent mechanism
- PII shared with third parties without consent
- No data minimization (collecting everything "just in case")
- Indefinite data retention
- No way for users to access/delete their data
- PII used for purposes beyond original intent
- Children's data collected without parental consent

**GDPR RIGHTS (must implement):**
- **Right to access** - Users can request their data
- **Right to rectification** - Users can correct errors
- **Right to erasure** ("right to be forgotten")
- **Right to data portability** - Export data in machine-readable format
- **Right to object** - Object to processing
- **Right to restrict processing**

**REQUIREMENTS:**
- **Lawful basis** for processing (consent, contract, legitimate interest, etc.)
- **Purpose limitation** - Only use for stated purpose
- **Data minimization** - Collect only what's necessary
- **Storage limitation** - Don't keep forever
- **Transparency** - Clear privacy policy
- **Accountability** - Document compliance

**MITIGATIONS:**
- Implement consent management system
- Create clear, accessible privacy policy
- Build data access/deletion endpoints
- Anonymize or pseudonymize when possible
- Set automatic deletion schedules
- Get parental consent for children (<13 COPPA, <16 GDPR)
- Document lawful basis for each data type

### 3. SURVEILLANCE & TRACKING

**Types of Surveillance:**
- **Location tracking** - GPS, cell tower, WiFi triangulation
- **Behavioral tracking** - Browsing history, app usage, click patterns
- **Video surveillance** - CCTV with AI analysis
- **Audio recording** - Microphone access
- **Screen recording** - What users see/do
- **Keylogging** - Tracking keystrokes
- **Cross-device tracking** - Linking multiple devices
- **Cross-site tracking** - Following across websites

**RED FLAGS:**
- Continuous location tracking without user awareness
- Background camera/microphone access
- No ability to disable tracking
- Tracking in sensitive locations (home, healthcare, places of worship)
- Selling location data to third parties
- Combining location with identity
- No data retention limits on tracking data
- Tracking children without parental consent
- Real-time biometric surveillance in public spaces

**REGULATIONS:**
- **GDPR** - Requires consent for tracking, especially cross-site
- **ePrivacy Directive** - Cookie consent requirements
- **CCPA** - Right to know what's collected, opt-out of sale
- **EU AI Act** - Restricts real-time biometric identification in public

**REQUIREMENTS:**
- **Opt-in consent** for tracking (not pre-checked boxes)
- **Clear disclosure** of what's tracked
- **Easy opt-out** mechanisms
- **No tracking walls** (blocking access if user declines)
- **Granular controls** (track location vs track behavior)
- **Data minimization** in tracking
- **Deletion mechanisms**

**MITIGATIONS:**
- Implement tracking consent banners (compliant with GDPR)
- Provide location permission prompts
- Allow users to disable tracking
- Don't track in sensitive areas
- Don't combine tracking data with identity
- Delete tracking data regularly
- Don't sell location/tracking data
- Be transparent about what's tracked

### 4. EMOTION DETECTION & INFERENCE

**What is it:**
- AI analyzing facial expressions, voice, or text to infer emotional state
- Different from detecting "happy face" vs inferring "person is happy"

**EU AI ACT RESTRICTIONS:**
- **BANNED in workplaces** (except medical/safety reasons)
- **BANNED in education** (except medical/safety reasons)
- **HIGH-RISK in other contexts** (customer service, etc.)

**RED FLAGS:**
- Emotion detection in workplace for productivity monitoring
- Emotion analysis in schools/universities
- Using emotions to make decisions about people (hiring, promotions)
- No disclosure that emotions are being analyzed
- Persistent emotion profiles over time
- Combining emotion data with identity

**PRIVACY CONCERNS:**
- Reveals internal mental state (like health data)
- Can infer protected characteristics
- Power imbalance (employer/employee, teacher/student)
- Chilling effect on expression and behavior

**MITIGATIONS:**
- Don't use in workplace/education
- If used elsewhere, get explicit consent
- Don't create persistent profiles
- Analyze locally, don't store emotion data
- Add mathematical noise (differential privacy)
- Time-limit emotion data (delete within hours)
- Transparent disclosure when active

### 5. PROFILING & AUTOMATED DECISIONS

**What is it:**
- Using personal data to evaluate aspects of a person
- Making automated decisions that significantly affect people

**Types:**
- **Credit scoring**
- **Insurance risk assessment**
- **Employment screening**
- **Targeted advertising**
- **Price discrimination**
- **Content personalization**
- **Social scoring**

**GDPR Article 22:**
- Right to NOT be subject to solely automated decisions with legal/significant effects
- Exceptions: Contract necessity, legal requirement, explicit consent
- Even with exceptions, must implement safeguards

**RED FLAGS:**
- Automated decisions with no human review
- No explanation of decision logic
- Can't challenge automated decisions
- Profiling based on special category data
- Profiles sold/shared without consent
- Function creep (profile for X, use for Y)
- No way to opt-out of profiling

**REQUIREMENTS:**
- **Human review** for significant decisions
- **Explainability** - Tell people how decisions are made
- **Right to challenge**
- **Data minimization** in profiles
- **Purpose limitation**
- **Consent** for marketing profiling

**MITIGATIONS:**
- Implement human-in-the-loop for significant decisions
- Provide decision explanations
- Allow users to challenge decisions
- Don't use special category data for profiling
- Separate profiling consent from service access
- Give granular profiling controls

### 6. CHILDREN'S PRIVACY

**Extra Protection Required:**
- **Age verification** mechanisms
- **Parental consent** (<13 COPPA, <16 GDPR)
- **Age-appropriate privacy notices**
- **No targeted advertising to children**
- **Data minimization** - only what's necessary
- **No selling children's data**

**RED FLAGS:**
- No age verification
- Collecting data from children without parental consent
- Behavioral advertising to children
- Location tracking of children
- Biometric data from minors
- Social media profiling of children

**REGULATIONS:**
- **COPPA (US)** - Children under 13
- **GDPR (EU)** - Children under 16 (member states can lower to 13)
- **UK Age Appropriate Design Code**
- **CCPA** - Enhanced protections for minors

**REQUIREMENTS:**
- Verifiable parental consent
- Age-appropriate privacy notices (simple language)
- Default to highest privacy settings
- No data used for profiling/targeting
- Clear parental controls
- Easy deletion mechanisms

**MITIGATIONS:**
- Implement robust age verification
- Get parental consent before collection
- Design privacy-by-default for children
- Don't track/profile children
- Provide parental dashboards
- Regular data deletion for child accounts

### 7. DATA SHARING & THIRD PARTIES

**RED FLAGS:**
- Sharing personal data without consent
- Selling user data
- Unclear third-party relationships in privacy policy
- No data processing agreements with vendors
- Data transferred internationally without safeguards
- No ability to object to data sharing
- Sharing more data than necessary with third parties

**GDPR REQUIREMENTS:**
- **Data Processing Agreements** with all vendors
- **International transfer** safeguards (Standard Contractual Clauses, adequacy decisions)
- **Transparent disclosure** of all third parties
- **Purpose limitation** - third parties bound by same limits
- **User consent** for non-essential sharing

**MITIGATIONS:**
- Audit all third-party data flows
- Implement Data Processing Agreements
- Use Standard Contractual Clauses for international transfers
- Disclose all data recipients in privacy policy
- Get consent for data sales/sharing
- Minimize data shared with vendors
- Regular vendor security assessments

### 8. CONSENT MANAGEMENT

**Invalid Consent Under GDPR:**
- Pre-checked boxes
- Bundled consent (must accept all or nothing)
- Consent walls (blocking service if declined)
- Unclear or vague language
- No easy withdrawal mechanism
- Power imbalance (employer/employee)
- Children without parental consent

**Valid Consent Requires:**
- **Freely given** - Real choice, no detriment if declined
- **Specific** - Clear what's consented to
- **Informed** - Full information provided
- **Unambiguous** - Clear affirmative action
- **Granular** - Separate consent for different purposes
- **Withdrawable** - Easy to revoke

**RED FLAGS:**
- Pre-checked consent boxes
- "By using this service, you consent" (not valid)
- Can't access service without consenting to everything
- No way to withdraw consent
- Consent for vague purposes
- Same consent for multiple unrelated things

**MITIGATIONS:**
- Implement proper consent banners/forms
- Granular consent options (choose what to consent to)
- Easy consent withdrawal
- Document consent decisions
- Re-prompt for consent when purposes change
- Don't block service for optional data collection

## Assessment Checklist

### Biometric Data
- [ ] Is biometric data collected (faces, fingerprints, voice)?
- [ ] Is there explicit written consent?
- [ ] Is there a clear, specific purpose?
- [ ] Are retention limits defined?
- [ ] Can users delete their biometric data?
- [ ] Is DPIA conducted?
- [ ] Does it violate EU AI Act prohibitions?

### PII Collection
- [ ] What personal data is collected?
- [ ] Is there a lawful basis (consent, contract, etc.)?
- [ ] Is there a clear privacy policy?
- [ ] Can users access their data?
- [ ] Can users delete their data?
- [ ] Is data minimized?
- [ ] How long is data retained?

### Tracking & Surveillance
- [ ] What tracking occurs (location, behavior, etc.)?
- [ ] Is there clear consent for tracking?
- [ ] Can users opt-out easily?
- [ ] Is tracking data combined with identity?
- [ ] How long is tracking data kept?

### Children
- [ ] Are children users?
- [ ] Is there age verification?
- [ ] Is parental consent obtained?
- [ ] Is data minimized for children?
- [ ] No profiling/targeting of children?

### Third Parties
- [ ] Is data shared with third parties?
- [ ] Are third parties disclosed?
- [ ] Are there data processing agreements?
- [ ] Is there consent for data sharing?
- [ ] Are international transfers protected?

### Consent
- [ ] Is consent freely given?
- [ ] Is consent specific and informed?
- [ ] Can consent be withdrawn easily?
- [ ] Is consent granular?
- [ ] Are there consent walls?

### User Rights
- [ ] Can users access their data?
- [ ] Can users delete their data?
- [ ] Can users export their data?
- [ ] Can users object to processing?
- [ ] Is there a way to challenge automated decisions?

## Severity Levels

**CRITICAL** - Clear privacy law violations, high regulatory risk
- Collecting biometric data without consent
- Children's data without parental consent
- No way to delete personal data
- Violates EU AI Act prohibitions (facial scraping, workplace emotion detection)

**HIGH** - Significant privacy issues, regulatory action likely
- No privacy policy
- Invalid consent mechanisms
- Excessive data collection
- No lawful basis for processing
- Selling user data without consent

**MEDIUM** - Privacy gaps, should fix to ensure compliance
- Unclear privacy notices
- Long data retention
- Limited user control
- Missing GDPR rights implementation

**LOW** - Best practices, enhance privacy
- Could improve consent flows
- Could implement more granular controls
- Could add privacy-enhancing technologies

## Response Framework

When identifying privacy issues, provide:

1. **Privacy Violation Type**
2. **Severity Level**
3. **Specific Issue** (quote code, describe practice)
4. **User Impact** (how privacy is violated)
5. **Regulatory Risk** (GDPR fines, BIPA lawsuits, etc.)
6. **Applicable Regulations**
7. **Required Actions**
8. **Mitigation Code/Process**

## Examples

### Example 1: Facial Recognition Without Consent (CRITICAL)

```python
# CRITICAL PRIVACY VIOLATION
import face_recognition

def process_user_photo(image_file):
    # No consent obtained!
    face_encoding = face_recognition.face_encodings(image_file)[0]
    
    # Storing biometric data
    db.store_face_template(user_id, face_encoding)
    
    return "Face registered"
```

**Violation:** Biometric Data Collection Without Consent
**Severity:** CRITICAL
**Regulations Violated:** GDPR Article 9, Illinois BIPA, CCPA

**User Impact:**
- Biometric data collected without knowledge/consent
- No ability to opt-out or delete
- Permanent unique identifier created

**Regulatory Risk:**
- GDPR: Up to €20M or 4% global revenue
- BIPA: $1,000-$5,000 per violation (statutory damages)
- Class action lawsuit risk

**Required Actions:**
1. Obtain explicit written consent BEFORE collection
2. Provide clear biometric privacy policy
3. Implement deletion mechanisms
4. Set retention limits
5. Conduct DPIA

**Mitigation:**
```python
def process_user_photo(image_file, consent_granted=False):
    # Check consent first
    if not consent_granted:
        return {
            "error": "Biometric consent required",
            "consent_form_url": "/biometric-consent"
        }
    
    # Verify written consent exists
    if not db.has_biometric_consent(user_id):
        raise ValueError("No valid biometric consent on file")
    
    # Process with consent
    face_encoding = face_recognition.face_encodings(image_file)[0]
    
    # Store with retention limit
    db.store_face_template(
        user_id, 
        face_encoding,
        expires_at=datetime.now() + timedelta(days=90)
    )
    
    # Log consent
    db.log_biometric_processing(user_id, "face_encoding", datetime.now())
    
    return "Face registered with consent"
```

### Example 2: Workplace Emotion Detection (CRITICAL)

```javascript
// CRITICAL - EU AI ACT VIOLATION
class ProductivityMonitor {
  async analyzeEmployee(employeeId) {
    const webcamFeed = await getWebcamStream(employeeId);
    
    // BANNED under EU AI Act Article 5(1)(f)
    const emotions = await emotionAI.analyze(webcamFeed);
    
    if (emotions.frustration > 0.7) {
      notifyManager(employeeId, "Employee showing signs of frustration");
    }
    
    return logProductivity(employeeId, emotions);
  }
}
```

**Violation:** Emotion Recognition in Workplace (EU AI Act Prohibition)
**Severity:** CRITICAL
**Regulations Violated:** EU AI Act Article 5(1)(f), GDPR Article 9

**User Impact:**
- Emotional state monitored without choice
- Creates chilling effect on behavior
- Power imbalance (can't refuse employer)
- Biometric data (facial analysis) processed

**Regulatory Risk:**
- EU AI Act: Prohibited practice, enforcement starting 2025
- GDPR: Special category data processing
- Employment law violations
- Employee lawsuits

**Required Actions:**
1. STOP using emotion detection in workplace immediately
2. Delete all collected emotion data
3. Don't use AI to monitor employee emotional state
4. If safety-critical need, get legal opinion

**Mitigation:**
```javascript
// COMPLIANT - Focus on objective productivity metrics
class ProductivityMonitor {
  async trackTaskCompletion(employeeId) {
    // Track objective work metrics only
    const tasks = await getCompletedTasks(employeeId);
    const hours = await getHoursLogged(employeeId);
    
    // NO facial analysis, NO emotion detection
    return {
      tasks_completed: tasks.length,
      hours_worked: hours,
      productivity_score: calculateScore(tasks, hours)
    };
  }
}

// If truly needed for safety (e.g., heavy machinery operator fatigue):
// 1. Get legal opinion
// 2. Limit to safety-critical roles
// 3. Detect fatigue/alertness (not emotions)
// 4. Transparent disclosure
// 5. Union/works council consultation
```

### Example 3: Children's App Without Parental Consent (CRITICAL)

```python
# CRITICAL PRIVACY VIOLATION
@app.route('/signup', methods=['POST'])
def create_account():
    username = request.json['username']
    email = request.json['email']
    age = request.json['age']
    
    # No age check or parental consent!
    user = User.create(username=username, email=email, age=age)
    
    # Start collecting data immediately
    track_user_behavior(user.id)
    
    return {"user_id": user.id}
```

**Violation:** Children's Data Without Parental Consent
**Severity:** CRITICAL
**Regulations Violated:** COPPA (US), GDPR Article 8 (EU)

**User Impact:**
- Children's data collected without parent knowledge
- Behavioral tracking of minors
- No parental controls

**Regulatory Risk:**
- FTC COPPA violations: $46,517 per violation
- GDPR: Up to €20M or 4% revenue
- Class action from parents

**Required Actions:**
1. Implement age verification
2. Get verifiable parental consent for <13 (COPPA) or <16 (GDPR)
3. Stop tracking children's behavior
4. Provide parental controls
5. Data minimization for children

**Mitigation:**
```python
@app.route('/signup', methods=['POST'])
def create_account():
    username = request.json['username']
    email = request.json['email']
    age = request.json['age']
    
    # Age check
    if age < 13:  # COPPA threshold
        return {
            "requires_parental_consent": True,
            "parent_consent_url": "/parental-consent",
            "message": "Users under 13 require parental consent"
        }
    
    if age < 16:  # GDPR threshold (check jurisdiction)
        # Verify parental consent
        parent_consent_token = request.json.get('parent_consent_token')
        if not verify_parental_consent(parent_consent_token):
            return {"error": "Parental consent required"}, 403
    
    # Create account with appropriate settings
    user = User.create(
        username=username,
        email=email,
        age=age,
        privacy_mode='child' if age < 16 else 'standard'
    )
    
    # NO behavioral tracking for children
    if age >= 16:
        track_user_behavior(user.id)
    
    return {"user_id": user.id}
```

### Example 4: Location Tracking Without Consent (HIGH)

```javascript
// HIGH PRIVACY ISSUE
function initializeApp() {
  // Start tracking immediately without asking
  navigator.geolocation.watchPosition(position => {
    sendToServer({
      latitude: position.coords.latitude,
      longitude: position.coords.longitude,
      timestamp: Date.now(),
      userId: getCurrentUser().id
    });
  });
}
```

**Violation:** Location Tracking Without Consent
**Severity:** HIGH
**Regulations Violated:** GDPR, ePrivacy Directive

**User Impact:**
- Continuous location monitoring without knowledge
- No ability to opt-out
- Location linked to identity

**Regulatory Risk:**
- GDPR violations
- Privacy law enforcement
- User trust damage

**Required Actions:**
1. Request location permission
2. Explain why location is needed
3. Provide opt-out mechanism
4. Don't link location to identity (if possible)
5. Set retention limits

**Mitigation:**
```javascript
async function requestLocationAccess() {
  // Explain purpose first
  const consent = await showLocationConsentDialog({
    title: "Location Access Request",
    message: "We'd like to access your location to show nearby restaurants",
    purposes: ["Find nearby restaurants", "Provide directions"],
    optional: true  // Not required for basic functionality
  });
  
  if (consent.granted) {
    // Request browser permission
    navigator.geolocation.watchPosition(
      position => {
        // Anonymize if possible
        sendToServer({
          latitude: roundToNearest(position.coords.latitude, 0.01),
          longitude: roundToNearest(position.coords.longitude, 0.01),
          timestamp: Date.now()
          // NO userId unless absolutely necessary
        });
      },
      error => console.error("Location error:", error),
      {
        enableHighAccuracy: false,  // Less precise = more private
        maximumAge: 60000  // Cache for 1 minute
      }
    );
    
    // Set auto-delete
    scheduleLocationDataDeletion(30);  // Delete after 30 days
  } else {
    // App works without location
    loadDefaultContent();
  }
}
```

## Key Regulations

- **GDPR (EU)** - General Data Protection Regulation
- **CCPA (California)** - California Consumer Privacy Act
- **CPRA (California)** - California Privacy Rights Act
- **BIPA (Illinois)** - Biometric Information Privacy Act
- **COPPA (US Federal)** - Children's Online Privacy Protection Act
- **ePrivacy Directive (EU)** - Cookie consent, tracking
- **EU AI Act** - Biometric systems, emotion recognition
- **UK GDPR** - UK version post-Brexit
- **LGPD (Brazil)** - Lei Geral de Proteção de Dados
- **PIPEDA (Canada)** - Personal Information Protection Act

## Privacy-Enhancing Technologies

- **Differential Privacy** - Add noise to protect individuals
- **Federated Learning** - Train models without centralizing data
- **Homomorphic Encryption** - Compute on encrypted data
- **Secure Multi-Party Computation** - Analyze without revealing
- **Edge Processing** - Process locally, don't send to servers
- **Anonymization** - Remove identifying information
- **Pseudonymization** - Replace identifiers with pseudonyms
- **Data Minimization** - Collect only what's needed

## Final Principles

1. **Privacy by Design** - Build privacy in from the start
2. **Privacy by Default** - Highest privacy settings as default
3. **Data Minimization** - Collect only what's necessary
4. **Purpose Limitation** - Use only for stated purpose
5. **Transparency** - Be clear about data practices
6. **User Control** - Give users control over their data
7. **Accountability** - Document compliance
8. **Consent** - Get real, informed consent

Privacy is a fundamental right. Respect it.
