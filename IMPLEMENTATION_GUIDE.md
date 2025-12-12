# 7D Framework Implementation Guide

This guide provides practical instructions for applying the 7D Candidate Evaluation Framework, whether manually (by recruiters) or automated (by software systems).

---

## For Recruiters (Manual Application)

### Evaluation Worksheet

Use this structured approach to score candidates:

#### Step 1: Preparation (2 minutes)

1. Read the job description and identify:
   - Core required skills (technical, domain, soft skills)
   - Experience level expected
   - Location and language requirements
   - Company culture signals (startup vs. enterprise, pace, values)

2. Read the candidate's CV/resume fully before scoring

#### Step 2: Score Each Dimension (8 minutes)

For each dimension, assign a score from 1-10 using the scoring guidance from the [Specification](SPECIFICATION.md#3-the-seven-dimensions).

**Worksheet:**

```
CANDIDATE: ________________________    JOB: ________________________

1. QUALIFICATION MATCH (1-10): ___
   Notes: _______________________________________________

2. CAPABILITY CONFIDENCE (1-10): ___
   Evidence of capability:
   □ Portfolio/projects described
   □ Quantified achievements present
   □ Technical depth demonstrated
   □ Problem-solving approach visible
   Notes: _______________________________________________

3. SITUATIONAL STABILITY (1-10): ___
   □ Location matches requirements
   □ Language requirements met
   □ Clear availability
   □ Motivation for role evident
   Notes: _______________________________________________

4. REWARD POTENTIAL (1-10): ___
   Unique value:
   □ Rare skills or perspective
   □ Leadership indicators
   □ Entrepreneurial experience
   □ High learning velocity
   Notes: _______________________________________________

5. CULTURAL FIT (1-10): ___
   Alignment with:
   □ Work style (pace, autonomy, collaboration)
   □ Values
   □ Communication style
   Notes: _______________________________________________

6. CAREER TRAJECTORY (1-10): ___
   Growth pattern:
   □ Expanding scope
   □ Skill acquisition
   □ Increasing impact
   Notes: _______________________________________________

7. COMPENSATION ALIGNMENT (1-10): ___
   Expectation signals:
   □ Current company type
   □ Seniority level
   □ Location/CoL
   □ Career stage
   Notes: _______________________________________________

---

AGGREGATE SCORE: ___ (Calculate using weighted average)

HIDDEN GEM? □ Yes □ No
If yes, reasoning: ___________________________________

RECOMMENDATION: □ Strong Yes □ Yes □ Maybe □ No □ Strong No

STRENGTHS (3-5):
1. _______________________________________________
2. _______________________________________________
3. _______________________________________________

CONCERNS (2-4):
1. _______________________________________________
2. _______________________________________________

```

#### Step 3: Calculate Aggregate Score (2 minutes)

**Simple Approach (Equal Weighting):**
```
Aggregate = (Sum of all 7 dimension scores) / 7 × 10
```

**Role-Weighted Approach:**

For most roles, use these approximate weights:
```
Aggregate = (
  Qualification × 0.25 +
  Capability × 0.20 +
  Situational × 0.10 +
  Reward × 0.20 +
  Culture × 0.12 +
  Trajectory × 0.08 +
  Compensation × 0.05
) × 10
```

Adjust weights based on role:
- **Technical roles:** Increase Capability weight
- **Volume hiring:** Increase Compensation and Situational weights
- **Leadership roles:** Increase Reward and Capability weights

#### Step 4: Hidden Gem Check

Flag as hidden gem if:
- High Capability (7+) + Low Qualification (≤6) → Self-taught or non-traditional path
- High Reward (8+) + Non-linear career → Entrepreneurial or high-growth potential
- High Trajectory (8+) + Short experience → Fast learner

**AND** candidate would likely be rejected by keyword-based ATS.

### Question Prompts for Each Dimension

Use these questions while reviewing the CV:

**Qualification Match:**
- Do they have the required technical skills?
- Is their experience level appropriate?
- Do they have transferable skills from adjacent domains?

**Capability Confidence:**
- Do they describe *what* they built and *how* they built it?
- Are achievements quantified or vague?
- Do they discuss technical decisions and trade-offs?

**Situational Stability:**
- Does their location match the requirement?
- Do they list required languages?
- Why are they looking for this specific role?

**Reward Potential:**
- Do they bring unique skills or perspectives?
- Is there evidence of leadership, mentorship, or ownership?
- Do they have entrepreneurial or innovation experience?

**Cultural Fit:**
- Does their communication style match the job description tone?
- Do their career choices align with the company's stage and values?
- Are they seeking autonomy or structure (match the culture)?

**Career Trajectory:**
- Is their scope of work expanding over time?
- Are they continuously learning new skills?
- Is their impact growing?

**Compensation Alignment:**
- What's their current company type (FAANG, startup, enterprise)?
- What seniority level are they at?
- Are they a career changer or traditional path?

### Calibration Exercises

**For Teams:**

1. **Anchor Establishment:** As a team, score 5 candidates together and discuss:
   - What does a "3" in Capability look like?
   - What does an "8" in Reward Potential look like?
   - When do we flag hidden gems?

2. **Independent Scoring:** Each team member scores 10 candidates independently

3. **Comparison Session:** Compare scores and discuss large discrepancies:
   - Why did you score Capability as 9 vs. my 6?
   - What evidence changed your Trajectory assessment?

4. **Refinement:** Update team scoring guidelines based on discussions

5. **Periodic Re-calibration:** Every quarter, review scoring consistency

---

## For Developers (Software Integration)

### Conceptual Architecture

A 7D evaluation system typically follows this pipeline:

```
[Job Description] + [Candidate CV]
            ↓
    ┌───────────────┐
    │  Extraction   │ → Skills, experience, education, signals
    └───────────────┘
            ↓
    ┌───────────────┐
    │ Dimension     │ → Score each dimension 1-10
    │ Scoring       │   (7 independent evaluations)
    └───────────────┘
            ↓
    ┌───────────────┐
    │ Bias          │ → Apply corrections for credentials,
    │ Correction    │   gaps, non-linear careers
    └───────────────┘
            ↓
    ┌───────────────┐
    │ Aggregate     │ → Weighted average → 0-100 score
    │ Calculation   │
    └───────────────┘
            ↓
    ┌───────────────┐
    │ Hidden Gem    │ → Pattern matching on dimension scores
    │ Detection     │
    └───────────────┘
            ↓
    ┌───────────────┐
    │ Explanation   │ → Strengths, concerns, recommendation
    │ Generation    │
    └───────────────┘
            ↓
      [Output JSON]
```

### Input Requirements

**Minimum Required:**
- `job_description` (string): Full text of job posting
- `candidate_cv` (string): Full text of resume/CV

**Optional (Improves Accuracy):**
- `job_location` (string): Geographic location requirement
- `job_languages` (array): Required languages
- `compensation_range` (object): Min/max budget
- `company_stage` (enum): startup | scaleup | enterprise
- `role_type` (enum): individual_contributor | manager | executive

### Processing Steps

#### 1. Extraction Phase

Extract structured data from unstructured text:

**From Job Description:**
```javascript
{
  required_skills: ["Python", "AWS", "SQL"],
  nice_to_have_skills: ["Docker", "Kubernetes"],
  experience_years: 5,
  education_level: "bachelor",  // or null if not required
  location: "San Francisco, CA",
  languages: ["English"],
  role_type: "Senior Backend Engineer",
  company_signals: {
    stage: "startup",
    pace: "fast",
    culture_keywords: ["ownership", "autonomy"]
  }
}
```

**From Candidate CV:**
```javascript
{
  name: "Alex Johnson",
  skills: ["Python", "PostgreSQL", "AWS", "React"],
  experience: [
    {
      title: "Backend Engineer",
      company: "TechCorp",
      duration_months: 36,
      achievements: [...],
      complexity_indicators: [...]
    }
  ],
  education: [{...}],
  total_experience_months: 60,
  location: "New York, NY",
  languages: ["English", "Spanish"],
  portfolio_urls: [...],
  career_gaps: []
}
```

**Technology Recommendation:** Use Large Language Models (Claude, GPT-4, etc.) for extraction as they handle unstructured text well.

#### 2. Dimension Scoring

Score each dimension independently using the extracted data and scoring guidance:

**Example Pseudocode:**

```python
def score_qualification_match(job_data, candidate_data):
    required_skills_present = len(
        set(candidate_data['skills']) & set(job_data['required_skills'])
    ) / len(job_data['required_skills'])

    experience_match = min(
        candidate_data['total_experience_months'] / (job_data['experience_years'] * 12),
        1.0
    )

    # Combine signals with weighting
    score = (required_skills_present * 0.6 + experience_match * 0.4) * 10

    # Apply transferable skills bonus
    if has_transferable_skills(candidate_data, job_data):
        score = min(score + 1, 10)

    return round(score)

def score_capability_confidence(job_data, candidate_data):
    # Look for evidence quality, not just presence
    portfolio_quality = assess_portfolio_complexity(candidate_data['experience'])
    quantification = count_quantified_achievements(candidate_data['experience'])
    depth_signals = find_depth_indicators(candidate_data['experience'])

    # Combine evidence strength
    score = calculate_evidence_score(portfolio_quality, quantification, depth_signals)

    return round(score)

# Similar functions for other 5 dimensions...
```

#### 3. Bias Correction

Apply corrections **after** initial scoring:

```python
def apply_bias_corrections(scores, candidate_data):
    # Credential bias correction
    if not has_traditional_degree(candidate_data) and has_strong_portfolio(candidate_data):
        # Don't penalize capability for lack of degree
        scores['capability_confidence'] = max(
            scores['capability_confidence'],
            assess_portfolio_based_capability(candidate_data)
        )

    # Career gap correction
    for gap in candidate_data['career_gaps']:
        if gap['reason'] in ['entrepreneurship', 'learning', 'side_projects']:
            # Boost trajectory and reward for productive gaps
            scores['career'] = min(scores['career'] + 1, 10)
            scores['reward'] = min(scores['reward'] + 1, 10)

    # Non-linear career correction
    if has_career_transitions(candidate_data):
        if shows_skill_expansion(candidate_data):
            # Career change with growth = positive
            scores['career'] = min(scores['career'] + 1, 10)

    return scores
```

#### 4. Aggregate Calculation

```python
def calculate_aggregate(scores, role_type='general'):
    weights = get_weights_for_role(role_type)

    aggregate = (
        scores['qualification'] * weights['qualification'] +
        scores['capability_confidence'] * weights['capability'] +
        scores['situational_stability'] * weights['situational'] +
        scores['reward'] * weights['reward'] +
        scores['culture'] * weights['culture'] +
        scores['career'] * weights['career'] +
        scores['compensation'] * weights['compensation']
    ) * 10  # Scale to 0-100

    return round(aggregate)

def get_weights_for_role(role_type):
    if role_type == 'technical':
        return {
            'qualification': 0.25,
            'capability': 0.25,
            'situational': 0.10,
            'reward': 0.20,
            'culture': 0.10,
            'career': 0.05,
            'compensation': 0.05
        }
    elif role_type == 'executive':
        return {
            'qualification': 0.20,
            'capability': 0.30,
            'situational': 0.05,
            'reward': 0.25,
            'culture': 0.10,
            'career': 0.05,
            'compensation': 0.05
        }
    # ... other role types
```

#### 5. Hidden Gem Detection

```python
def detect_hidden_gem(scores, candidate_data):
    # Pattern 1: High capability, low qualification (non-traditional)
    if scores['capability_confidence'] >= 7 and scores['qualification'] <= 6:
        if not has_traditional_credentials(candidate_data):
            return {
                'is_hidden_gem': True,
                'reasoning': 'Strong portfolio evidence despite non-traditional background'
            }

    # Pattern 2: High reward, non-linear career
    if scores['reward'] >= 8:
        if has_entrepreneurial_experience(candidate_data) or has_career_transition(candidate_data):
            return {
                'is_hidden_gem': True,
                'reasoning': 'Entrepreneurial experience with high value potential'
            }

    # Pattern 3: High trajectory, short experience
    if scores['career'] >= 8 and candidate_data['total_experience_months'] < 48:
        return {
            'is_hidden_gem': True,
            'reasoning': 'Rapid skill acquisition and growth trajectory'
            }

    return {'is_hidden_gem': False, 'reasoning': None}
```

### Output Format Specification

Your system should produce JSON matching this schema:

```json
{
  "scores": {
    "qualification": 7,
    "capability_confidence": 8,
    "situational_stability": 9,
    "reward": 8,
    "culture": 7,
    "career": 9,
    "compensation": 6
  },
  "aggregate_score": 77,
  "recommendation": "yes",
  "confidence_level": "high",
  "summary": "Strong backend engineer with solid Python experience and proven AWS deployment skills. Self-taught background demonstrates high learning velocity. Location mismatch (NY → SF) is primary concern but candidate mentions willingness to relocate.",
  "strengths": [
    "Deployed production systems handling 50k+ requests/second",
    "Self-taught Python mastery with strong fundamentals demonstrated",
    "Open-source contributions show technical depth",
    "Rapid skill acquisition (AWS proficiency gained in 6 months)"
  ],
  "concerns": [
    "Located in NY, role requires SF (relocation needed)",
    "No formal CS education (mitigated by portfolio strength)",
    "Limited experience with Kubernetes (nice-to-have skill)"
  ],
  "hidden_gem": {
    "is_hidden_gem": true,
    "reasoning": "Traditional ATS would reject due to lack of CS degree and exact 5-year requirement, but candidate's portfolio demonstrates exceptional capability and learning velocity"
  }
}
```

### API Design Considerations

If exposing 7D as an API:

**Endpoint:**
```
POST /api/v1/evaluate
```

**Request:**
```json
{
  "job_description": "Full text of job posting...",
  "candidate_cv": "Full text of CV...",
  "options": {
    "role_type": "technical",
    "include_improvements": false
  }
}
```

**Response:**
```json
{
  "evaluation": { ... },
  "processing_time_ms": 2340,
  "version": "1.0.0"
}
```

### Testing Approach

**Unit Tests:**
- Test each dimension scorer independently
- Test bias correction rules
- Test aggregate calculation with various weight profiles
- Test hidden gem detection patterns

**Integration Tests:**
- End-to-end evaluation with known candidates
- Compare automated scores to human expert scores
- Test edge cases (minimal CVs, very long CVs, multilingual)

**Validation Dataset:**
- Collect 100+ human-labeled evaluations
- Measure correlation between automated and human scores
- Target: 85%+ agreement on recommendation level

**Quality Metrics:**
- Score distribution should be roughly normal
- Hidden gem detection rate: 10-20%
- Dimension scores should vary (not all identical)

---

## Calibration

### For Manual Application

**Process:**

1. **Baseline:** Score 20 candidates individually
2. **Group Review:** Team discusses scores for 5 candidates
3. **Alignment:** Identify and resolve scoring discrepancies
4. **Anchor Examples:** Document clear examples for each score level
5. **Practice:** Score 10 more candidates
6. **Validation:** Measure inter-rater reliability (should be >80% agreement within ±1 point)

### For Automated Systems

**Calibration Workflow:**

1. **Human Labeling:** Expert recruiters score 100+ candidates
2. **Training:** Tune model/weights to minimize divergence from human scores
3. **Validation:** Test on held-out set (20% of labeled data)
4. **Metrics:**
   - Dimension score MAE (Mean Absolute Error) < 1.5
   - Aggregate score MAE < 10
   - Recommendation agreement > 85%
5. **Monitoring:** Track score distribution over time, flag drift

---

## Quality Assurance

### Process Validation

**Distribution Checks:**
- Aggregate scores should follow roughly normal distribution
- Dimension scores should vary (if all identical, evaluation too shallow)
- Hidden gem rate: 10-20% (too high = false positives, too low = missing them)

**Consistency Checks:**
- Same candidate re-evaluated should score within ±5 points
- Similar candidates should have similar scores
- Scores should correlate with eventual hire outcomes

### Outcome Validation

Track these metrics to validate the framework is working:

| Metric | Target | Measurement |
|--------|--------|-------------|
| Interview-to-offer rate | Increase 15-30% | Compare pre/post 7D implementation |
| Offer acceptance rate | Increase 10-20% | Better situational fit assessment |
| 90-day retention | Increase 10-15% | Better cultural fit |
| Performance ratings | Correlation >0.6 | High scores → high performers |
| Time-to-hire | Decrease 20-30% | Better prioritization |

---

## Common Implementation Challenges

### Challenge 1: Insufficient CV Information

**Problem:** Candidate CV is very sparse (< 200 words)

**Solution:**
- Assign neutral scores (5/10) to dimensions lacking data
- Lower confidence_level to "low"
- Flag in concerns: "Limited information available for assessment"

### Challenge 2: Multilingual Content

**Problem:** Job in English, CV in Spanish

**Solution:**
- Translate CV to job language for comparison
- Preserve original language for quoted skills
- Note language match/mismatch in Situational Stability

### Challenge 3: Weighting Disagreement

**Problem:** Team disagrees on dimension weights

**Solution:**
- Start with general weights (Qualification=0.25, Capability=0.20, Reward=0.20)
- Adjust based on role-specific needs
- Document weight rationale
- Review hire outcomes to validate

### Challenge 4: Hidden Gem False Positives

**Problem:** Flagging too many hidden gems

**Solution:**
- Tighten detection criteria (require higher capability score)
- Require multiple signals (not just one pattern)
- Validate: Do flagged hidden gems actually perform well when hired?

---

## Example Workflows

### Workflow 1: High-Volume Screening

1. Automated 7D evaluation of all applicants
2. Filter: Keep aggregate ≥ 60
3. Human review: Prioritize 75+ scores and all hidden gems
4. Interview candidates scoring 75+
5. Maybe-pile (60-74): Review if time allows

### Workflow 2: Executive Search

1. Manual 7D evaluation by experienced recruiter
2. Custom weights: High Capability (0.30), High Reward (0.25)
3. Accept Compensation mismatch if Capability is exceptional
4. Deep interview for any candidate ≥70
5. Reference checks focus on dimension-specific concerns

### Workflow 3: Hybrid Approach

1. Automated 7D screening (filter out <50)
2. Human review of 50-74 range (context-dependent decisions)
3. Auto-interview 75+ scores
4. Manual review all hidden gems regardless of aggregate score

---

## Further Resources

- [Specification Document](SPECIFICATION.md) - Full framework details
- [Schema Files](schema.yaml) - Machine-readable specifications
- [Example Evaluations](examples/) - Sample outputs

For automated 7D evaluation, visit [https://tanova.ai](https://tanova.ai)
