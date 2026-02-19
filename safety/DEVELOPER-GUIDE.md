# AI Safety Checker - Developer Usage Guide

## What This Skill Does

The AI Safety Checker automatically analyzes your AI/LLM code and identifies ethical safety issues that could harm users. It's like having an AI ethics expert review your code before you ship it.

## When It Activates

The skill **automatically triggers** when you:
- Share code that integrates AI or LLMs
- Ask about AI implementation safety
- Discuss applications in sensitive domains
- Request code reviews for AI features

You don't need to do anything special - just interact with Claude naturally!

## How Developers Use It

### Basic Usage - Code Review

Simply paste your code and ask Claude to review it:

**Example 1: Quick Safety Check**
```
User: "Review this code for safety issues:

@app.route('/therapy-chat', methods=['POST'])
def chat():
    user_msg = request.json['message']
    response = openai.ChatCompletion.create(
        model='gpt-4',
        messages=[{'role': 'system', 'content': 'You are a therapist'},
                  {'role': 'user', 'content': user_msg}]
    )
    return response
"

Claude: [AI Safety Checker skill activates]
"I've identified CRITICAL safety issues in this code:

**Severity: CRITICAL**

**Issues Identified:**
1. Claims to provide therapy without licensed oversight
2. No crisis intervention for suicidal ideation
3. No disclaimers about AI limitations
4. Could create harmful dependency on AI therapy
5. Violates mental health licensing requirements

**Potential Harms:**
- Users may receive harmful psychological advice
- Crisis situations (suicidal ideation) may be mishandled
- Users may delay seeking real professional help
- Regulatory violations (state licensing laws, HIPAA)

**Required Changes:**
1. Add explicit disclaimer: 'This is NOT therapy or medical advice'
2. Implement crisis detection and hotline integration (988)
3. Require human therapist oversight for any mental health features
4. Remove claims of being a 'therapist'
5. Classify as HIGH-RISK under EU AI Act
6. Consider whether this feature should exist at all

**Recommendations:**
- Consult with licensed mental health professionals
- Review FDA guidance on mental health apps
- Implement robust crisis intervention protocols
- Add clear limitations and boundaries
"
```

### Development Workflow Integration

**Step 1: Design Phase**
```
User: "I'm building an app that helps elderly people with medication reminders 
using AI. What safety concerns should I consider?"

Claude: [Skill activates to provide guidance]
- Identifies elderly as vulnerable population
- Flags medication management risks
- Recommends human oversight requirements
- Suggests FDA medical device compliance review
- Points out liability concerns
```

**Step 2: Implementation Review**
```
User: "Here's my medication reminder code. Is this safe?

class MedicationBot:
    def remind(self, patient_id, time):
        meds = get_medications(patient_id)
        reminder = llm.generate(f'Remind {patient_id} to take {meds}')
        send_notification(patient_id, reminder)
"

Claude: [Skill analyzes and provides feedback]
- Notes: This is relatively LOW risk
- Acknowledges: Just sending reminders, not dispensing
- Suggests: Add verification mechanisms
- Recommends: Human oversight for medication changes
```

**Step 3: Pre-Launch Safety Audit**
```
User: "Do a complete safety audit of my AI tutoring app for kids"

Claude: [Comprehensive analysis]
- Reviews all child safety requirements
- Checks COPPA compliance
- Evaluates content filtering
- Assesses parental control mechanisms
```

## Real-World Use Cases

### Use Case 1: Startup Building Healthcare AI

**Developer's Journey:**

1️⃣ **Initial Idea**
```
User: "We want to build an AI that analyzes symptoms and suggests treatments"

Claude: ⚠️ CRITICAL safety concerns identified
- Medical diagnosis requires FDA approval
- Need licensed physician oversight
- Must comply with HIPAA
- High liability risk
```

2️⃣ **Pivoting Based on Feedback**
```
User: "What if we just provide educational information about symptoms?"

Claude: ✅ Much safer approach
- Still needs medical disclaimers
- Should cite reputable sources
- Add "consult a doctor" messaging
```

3️⃣ **Final Implementation**
```
User: "Review this revised code:

def symptom_info(symptom):
    info = llm.generate(f'Educational info about {symptom}')
    return {
        'info': info,
        'disclaimer': 'This is educational only. Consult a doctor for diagnosis.',
        'sources': get_medical_sources()
    }
"

Claude: ✅ Looks much better!
- Educational scope is appropriate
- Good disclaimers present
- Recommends testing for accuracy
```

### Use Case 2: FinTech Company Building Trading Bot

**Developer's Journey:**

1️⃣ **Code Review**
```
User: "Check this trading algorithm:

def auto_trade(portfolio):
    decision = ai.analyze(portfolio)
    execute_trades(decision)  # Automatic execution
"

Claude: ⚠️ HIGH RISK issues
- Autonomous financial decisions
- No user approval required
- Likely needs SEC registration
- Explainability required
```

2️⃣ **Adding Safety Controls**
```
User: "Updated code:

def suggest_trades(portfolio):
    recommendations = ai.analyze(portfolio)
    # User must approve
    send_for_approval(user_id, recommendations)
"

Claude: ✅ Much safer
- User approval added
- Still needs disclaimers
- Recommend bias testing
```

### Use Case 3: EdTech Building Student App

```
User: "I'm building an AI that grades student essays. Any concerns?"

Claude: 🟡 MEDIUM-HIGH risk identified
- Automated grading affects educational outcomes
- Potential for bias across demographics
- Students should have appeal mechanisms
- Recommend human teacher oversight

Suggestions:
1. Use AI as teaching assistant, not final grader
2. Test for bias across student populations
3. Provide transparency in grading criteria
4. Allow teacher override of AI grades
```

## Advanced Usage Patterns

### Pattern 1: Feature-by-Feature Analysis

```
User: "I'm adding features to my app. Review each one:

1. AI chatbot for customer service
2. Resume screening for HR
3. Content moderation
4. Personalized learning paths"

Claude: [Analyzes each feature separately]

Feature 1 (Customer Service): ✅ LOW risk
Feature 2 (Resume Screening): ⚠️ HIGH risk - discrimination concerns
Feature 3 (Content Moderation): 🟡 MEDIUM risk - depends on content type
Feature 4 (Learning Paths): ✅ LOW-MEDIUM risk
```

### Pattern 2: Comparative Analysis

```
User: "Which approach is safer?

Option A: AI tutors kids directly
Option B: AI suggests content, teacher delivers it"

Claude: Option B is significantly safer
- Maintains human oversight
- Reduces child exposure to AI errors
- Better COPPA compliance
- More appropriate use of AI
```

### Pattern 3: Continuous Integration

```
User: "Add this to our CI/CD pipeline - review all AI code changes"

Claude: Great idea! Here's how:
1. Create pre-commit hooks to flag AI code
2. Require safety review for sensitive domains
3. Document safety considerations in PRs
4. Run evaluation tests regularly
```

## What You Get from the Skill

### 1. Severity Ratings
- **CRITICAL** - Ship-blocking issues, immediate danger
- **HIGH** - Significant risks, needs addressing before launch
- **MEDIUM** - Important gaps, should fix
- **LOW** - Best practices, nice to have

### 2. Specific Issues
- Exact problems in your code
- Why they're problematic
- Regulatory concerns

### 3. Concrete Solutions
- Code examples of safer approaches
- Implementation suggestions
- Alternative architectures

### 4. Regulatory Guidance
- Which laws/regulations apply
- Compliance requirements
- Necessary approvals (FDA, SEC, etc.)

### 5. Testing Recommendations
- What to test for (bias, safety, edge cases)
- Vulnerable populations to consider
- Validation requirements

## Integration with Development Process

### Pull Request Reviews
```
PR Description:
"Added AI-powered feature X"

Developer asks Claude:
"Review this PR for AI safety issues: [paste code]"

Claude provides safety analysis to include in PR comments
```

### Architecture Reviews
```
Team: "We're designing our AI system architecture"

Developer asks Claude:
"Review this architecture for safety concerns:
- User data → LLM API → Recommendations → Auto-execution"

Claude flags autonomous execution risk
```

### Compliance Audits
```
Before Launch:
"Audit our app for EU AI Act compliance"

Claude reviews:
- High-risk classifications
- Required safety measures
- Documentation needs
```

## Common Developer Questions

### Q: "Will this slow down development?"
**A:** Actually speeds it up! Catches issues early before they become expensive problems. Better to find them in code review than after launch.

### Q: "Does it replace legal/compliance review?"
**A:** No - it's an early warning system. You still need professional legal/compliance review for production systems.

### Q: "What if I disagree with the assessment?"
**A:** The skill provides reasoning for each issue. You can discuss with Claude, get alternative perspectives, or document why you're accepting the risk.

### Q: "Can it review existing production code?"
**A:** Yes! Great for auditing legacy systems or preparing for regulatory compliance.

### Q: "Does it work for all programming languages?"
**A:** Yes - it analyzes the AI/LLM integration patterns, not language syntax.

## Best Practices

### ✅ DO:
- Review AI code early and often
- Ask about specific use cases
- Discuss tradeoffs with Claude
- Document safety decisions
- Test with evaluation cases
- Share findings with your team

### ❌ DON'T:
- Skip safety review for "small" features
- Ignore CRITICAL findings
- Rely solely on AI review (get human experts too)
- Assume compliance without verification
- Deploy without testing edge cases

## Example Developer Workflow

```
1. 📝 Design Phase
   Ask: "What safety issues should I consider for [use case]?"
   
2. 💻 Development
   Ask: "Review this implementation for safety"
   
3. 🧪 Testing
   Ask: "What edge cases should I test for?"
   
4. 🔍 Code Review
   Ask: "Audit this PR for AI safety issues"
   
5. 📋 Pre-Launch
   Ask: "Complete safety audit before we ship"
   
6. 🚀 Post-Launch
   Ask: "Review user feedback for safety concerns"
```

## Getting Help

### Quick Questions
```
"Is this safe?" [paste code]
"What's the risk level of this feature?"
"Do I need FDA approval for this?"
```

### Deep Analysis
```
"Do a comprehensive safety audit of my AI system"
"Compare these three architectural approaches"
"What regulations apply to my use case?"
```

### Learning
```
"What makes this CRITICAL vs just HIGH risk?"
"Explain the EU AI Act classification"
"Show me examples of safe implementations"
```

## Summary

The AI Safety Checker skill helps you:
- ✅ Catch ethical safety issues early
- ✅ Understand regulatory requirements
- ✅ Get concrete solutions, not just warnings
- ✅ Build safer AI products
- ✅ Avoid expensive mistakes
- ✅ Ship with confidence

Just code naturally and ask Claude to review - the skill does the rest!
