# The 7D Candidate Evaluation Framework
## Specification v1.0

### Abstract

The 7D Candidate Evaluation Framework is an open methodology for multi-dimensional candidate assessment that addresses the fundamental limitations of keyword-based screening systems. Traditional Applicant Tracking Systems (ATS) filter candidates through keyword matching and credential verification, systematically excluding exceptional self-taught professionals, career changers, and entrepreneurs who lack conventional backgrounds but possess strong capability and high growth potential.

This framework defines seven independent dimensions of candidate evaluation—Qualification Match, Capability Confidence, Situational Stability, Reward Potential, Cultural Fit, Career Trajectory, and Compensation Alignment—that combine to produce a holistic assessment. The methodology prioritizes evidence over claims, capability over credentials, and trajectory over static snapshots.

Created by Tanova (Pedersen Consulting) and released under Creative Commons Attribution 4.0 (CC BY 4.0), this specification serves as a reference for researchers, practitioners, and developers implementing AI-driven recruitment systems. The framework is implementation-agnostic and can be applied manually by recruiters or automated through software systems.

---

## 1. Introduction

### 1.1 The Problem with Keyword-Based Screening

Modern recruitment relies heavily on Applicant Tracking Systems that filter candidates using:
- **Keyword density matching:** Resume must contain exact phrases from job description
- **Credential verification:** Specific degrees, certifications, or company names required
- **Linear career progression:** Gaps, transitions, or non-traditional paths trigger rejection
- **Explicit skill listings:** Transferable skills from adjacent domains ignored

This approach systematically excludes:
- Self-taught professionals with deep practical knowledge
- Entrepreneurs with business-building experience
- Career changers with transferable expertise
- Candidates from underrepresented backgrounds with non-linear paths

These "hidden gems" often become high-performing hires when given the opportunity, yet they are filtered out before human review.

### 1.2 The Need for Multi-Dimensional Evaluation

A candidate's fit for a role cannot be reduced to a single binary decision (qualified/unqualified). Effective evaluation requires assessing multiple independent facets:

- **Can they do the job?** (Capability assessment)
- **Will they join and stay?** (Situational factors)
- **What's the upside if they succeed?** (Potential analysis)
- **How well do they match the culture?** (Fit evaluation)
- **Where is their career heading?** (Trajectory analysis)
- **Will compensation align?** (Economic feasibility)

The 7D Framework provides a structured methodology for evaluating each dimension independently, then combining them into a composite assessment that accounts for role-specific priorities.

### 1.3 Overview of the Seven Dimensions

The framework evaluates candidates across seven dimensions, each scored on a 1-10 scale:

1. **Qualification Match:** How well skills and experience align with job requirements
2. **Capability Confidence:** Degree of certainty that the candidate can perform core job functions
3. **Situational Stability:** Likelihood that the candidate will join, stay, and be available
4. **Reward Potential:** The upside value if this hire succeeds
5. **Cultural Fit:** Alignment with work style, values, and team dynamics
6. **Career Trajectory:** Growth pattern and learning velocity
7. **Compensation Alignment:** Likelihood of salary expectation alignment

These dimensions combine into a 0-100 aggregate score using role-dependent weighting that reflects the relative importance of each factor for the specific position.

---

## 2. Framework Philosophy

### 2.1 Capability Over Credentials

The framework values **demonstrated ability** over formal credentials. A self-taught developer with a portfolio of production systems may score higher in Capability Confidence than a recent computer science graduate with strong grades but limited practical experience. Evidence of problem-solving, project ownership, and technical depth matters more than the source of education.

### 2.2 Evidence Over Claims

Vague statements ("experienced in leadership") score lower than concrete achievements ("Led 8-person engineering team through SOC 2 compliance, reducing security findings from 47 to 0 over 6 months"). The framework looks for:
- Quantified outcomes
- Specific technical details
- Complexity indicators
- Problem-solving narratives

### 2.3 Trajectory Over Static Snapshot

Career velocity and learning patterns outweigh current state. A candidate showing rapid skill acquisition, expanding scope of work, and increasing impact demonstrates higher potential than a candidate with longer tenure but stagnant responsibilities. Non-linear career paths that show adaptability are valued, not penalized.

### 2.4 Hidden Gem Detection as a Core Principle

The framework explicitly identifies candidates that traditional systems would reject but who possess high potential:

**Hidden Gem Profile Indicators:**
- Non-traditional background (bootcamp, self-taught, career change)
- Evidence of rapid skill acquisition
- Entrepreneurial experience (including "failed" ventures)
- Strong fundamentals despite lacking keyword density
- Transferable skills from adjacent domains
- Portfolio evidence contradicting credential gaps

These candidates often become loyal, motivated, high-performers at more competitive compensation than traditional candidates.

---

## 3. The Seven Dimensions

### 3.1 Qualification Match

**Definition:** Qualification Match measures the degree to which a candidate's documented skills, experience, and background align with the explicit requirements stated in the job description.

**Rationale:** This dimension answers "Do they meet the basic requirements?" It accounts for both direct matches (exact skills/experience requested) and transferable capabilities (relevant experience from adjacent domains).

**Inputs Considered:**
- Presence of required technical skills
- Years of relevant experience
- Industry or domain expertise
- Educational background (when legitimately required for the role)
- Certifications or specialized training
- Evidence of transferable skills from related fields

**Scoring Guidance:**

| Score | Interpretation | Characteristics |
|-------|----------------|-----------------|
| 10 | Perfect match, exceeds requirements | Possesses all required skills plus advanced capabilities; experience level exceeds minimum requirements |
| 7-9 | Strong match, meets most requirements | Has 80%+ of required skills; minor gaps in nice-to-have areas; experience level appropriate |
| 4-6 | Partial match, transferable skills present | Has 50-75% of required skills; demonstrates transferable capabilities; can learn gaps with reasonable ramp time |
| 1-3 | Limited match, significant gaps | Lacks core required skills; experience significantly below requirements; no clear transfer path |

**Common Pitfalls This Dimension Corrects:**
- **Keyword inflation:** Prevents "keyword stuffing" from inflating qualification scores by requiring evidence depth
- **Credential proxy:** Separates formal credentials from actual capability—a bootcamp graduate with strong project portfolio may score 7-8 despite lacking a CS degree

**Example Scenario:**

*Job requirement:* "Senior Backend Engineer - 5+ years experience with distributed systems, proficiency in Go or Rust"

*Candidate A:* 7 years Java enterprise development, mentions "microservices" but no evidence of distributed systems complexity → Score: 5 (partial match, lacks depth)

*Candidate B:* 3 years as SRE at scale-up, detailed description of building distributed tracing system in Rust, contributed to open-source observability tools → Score: 8 (strong match despite slightly short tenure)

---

### 3.2 Capability Confidence

**Definition:** Capability Confidence measures the degree of certainty that a candidate can successfully perform the core functions of the role, based on demonstrated evidence rather than stated claims.

**Rationale:** This dimension answers "Can they actually do the job?" It goes beyond skill matching to assess problem-solving ability, technical depth, and the quality of evidence supporting capability claims.

**Inputs Considered:**
- **Portfolio evidence:** Complexity and quality of completed projects
- **Quantified achievements:** Measurable outcomes vs. vague responsibility statements
- **Depth indicators:** Architecture decisions made, scale handled, technical trade-offs discussed
- **Problem-solving signals:** How challenges were approached, not just what tools were used
- **Fundamental understanding:** Evidence of first-principles thinking vs. surface knowledge
- **Learning evidence:** Ability to acquire and apply new skills

**Scoring Guidance:**

| Score | Interpretation | Characteristics |
|-------|----------------|-----------------|
| 10 | Very high confidence | Proven ability at or above role level; strong fundamentals; portfolio demonstrates advanced problem-solving; exceeds capability requirements |
| 7-9 | High confidence | Solid skills with concrete evidence; minor learning curve expected; portfolio shows relevant complexity |
| 4-6 | Moderate confidence | Some skills need development but foundation is sound; can learn on the job; portfolio shows potential |
| 1-3 | Low confidence | Lacks fundamental skills; significant capability gaps; no evidence of relevant problem-solving |

**Common Pitfalls This Dimension Corrects:**
- **Resume inflation:** Claims of "expert-level" skills are validated against evidence depth
- **Recency bias:** Strong recent projects can outweigh dated earlier experience
- **Tooling focus:** Understanding problem-solving approaches matters more than knowing specific frameworks

**Example Scenario:**

*Role:* Machine Learning Engineer

*Candidate A:* Lists "TensorFlow, PyTorch, scikit-learn" but only describes running pre-built models → Score: 4 (surface knowledge, low confidence in ML capability)

*Candidate B:* Implemented customer churn prediction model, describes feature engineering decisions, details how they reduced false positive rate from 34% to 12% through threshold tuning and ensemble methods → Score: 9 (demonstrated deep understanding)

---

### 3.3 Situational Stability

**Definition:** Situational Stability assesses the likelihood that a candidate will accept an offer, remain in the role for a reasonable period, and be available to start within acceptable timeframes.

**Rationale:** This dimension answers "Will they join, stay, and be available?" High capability is irrelevant if a candidate is likely to decline the offer, leave within months, or cannot start for six months.

**Inputs Considered:**
- **Location alignment:** Geographic match with job requirements (office-based, remote policies, timezone constraints)
- **Language requirements:** Fluency in required languages for the role
- **Availability:** Notice period, current employment status
- **Motivation signals:** Why they're interested in this specific role
- **Retention likelihood:** Career stage, job-hopping patterns, commitment signals
- **Competing opportunities:** Other active interview processes
- **Life situation:** Relocation feasibility, family constraints

**Scoring Guidance:**

| Score | Interpretation | Characteristics |
|-------|----------------|-----------------|
| 10 | Very stable | Strong location match; clear availability; motivated by role specifics; retention signals strong; minimal flight risk |
| 7-9 | Stable | Good availability; reasonable retention likelihood; manageable location considerations |
| 4-6 | Moderate stability | Typical hiring uncertainties; some location or timing concerns; average retention likelihood |
| 1-3 | Unstable | Significant location mismatch; red flags around commitment; multiple competing offers; high flight risk |

**Special Considerations:**

**Consultant/Contract Roles:** Location penalties are reduced for short-term engagements (< 6 months), as temporary relocation is more feasible for high-value projects.

**Remote Roles:** Geographic location matters less, but timezone overlap and language requirements remain important.

**Common Pitfalls This Dimension Corrects:**
- **Passive candidates:** High interest signals from actively searching candidates vs. passive consideration
- **Relocation assumptions:** Explicit location validation rather than assuming candidates will relocate
- **Offer acceptance probability:** Factors beyond compensation that affect offer acceptance

**Example Scenario:**

*Job requirement:* "Backend Engineer - Copenhagen office, Danish team (English fluent acceptable)"

*Candidate A:* Based in London, all experience with remote companies, no Nordic languages listed → Score: 4 (location mismatch, likely unwilling to relocate for non-senior role)

*Candidate B:* Currently in Stockholm, mentions "looking to relocate to Copenhagen for family reasons," strong English, mentions Denmark in cover letter → Score: 9 (motivated relocation, clear availability)

---

### 3.4 Reward Potential

**Definition:** Reward Potential measures the upside value if this hire succeeds—the potential for exceptional performance, unique contributions, and value creation beyond the baseline job requirements.

**Rationale:** This dimension answers "What's the upside if they excel?" Not all hires carry equal potential. Some candidates offer transformational impact while others are solid contributors. Reward Potential captures the ceiling, not the floor.

**Inputs Considered:**
- **Unique skills or perspectives:** Capabilities that are rare or hard to find
- **Leadership indicators:** Evidence of mentorship, team building, or ownership
- **Innovation signals:** Entrepreneurial experience, side projects, creative problem-solving
- **Learning velocity:** Speed of skill acquisition and domain mastery
- **Multiplier effects:** Potential to elevate team performance, not just individual contribution
- **Fresh perspectives:** Non-traditional backgrounds that bring diverse approaches

**Scoring Guidance:**

| Score | Interpretation | Characteristics |
|-------|----------------|-----------------|
| 10 | Transformational hire | Could become team/domain leader; brings unique high-value skills; entrepreneurial drive; potential for 10x impact |
| 7-9 | High impact | Above-average performer; brings fresh perspective; growth into senior roles likely; valuable unique contributions |
| 4-6 | Solid contributor | Meets expectations; steady performer; reliable execution |
| 1-3 | Limited upside | Fills role minimally; no exceptional capabilities; baseline performer |

**Philosophy on Entrepreneurial Experience:**

Failed entrepreneurial ventures are scored as **high reward potential**, not high risk. Entrepreneurs who built (even unsuccessful) businesses demonstrate:
- Ownership mentality
- Problem-solving under constraints
- Rapid learning across domains
- Resilience and adaptability
- Bias toward action

**Common Pitfalls This Dimension Corrects:**
- **Risk aversion:** Traditional systems penalize career gaps from entrepreneurship; 7D values the learning
- **Credential obsession:** FAANG experience ≠ high reward; a self-taught engineer with novel approach may score higher
- **Conformity bias:** "Safe" hires with linear backgrounds may have lower upside than unconventional talent

**Example Scenario:**

*Role:* Product Manager

*Candidate A:* 8 years as PM at large enterprise, consistent role progression, strong execution skills → Score: 6 (solid contributor, predictable value)

*Candidate B:* 3 years PM at startup + 2 years building own failed SaaS product (reached $5k MRR before shutting down), wrote popular blog on product strategy → Score: 9 (high upside—entrepreneurial mindset, proven ability to build from zero, thought leadership)

---

### 3.5 Cultural Fit

**Definition:** Cultural Fit assesses alignment between the candidate's work style, values, communication approach, and the organization's culture as inferred from the job description and company context.

**Rationale:** This dimension answers "Will they thrive in this environment?" Technical capability alone does not ensure success. Cultural misalignment leads to low engagement, team friction, and early departure.

**Inputs Considered:**
- **Work style signals:** Preference for autonomy vs. structure, collaboration vs. independent work
- **Communication style:** Formal vs. informal, written vs. verbal emphasis
- **Values alignment:** Mission-driven vs. compensation-focused, growth mindset vs. stability-seeking
- **Pace preference:** Startup velocity vs. enterprise deliberation
- **Decision-making style:** Data-driven vs. intuition-based, consensus vs. decisive
- **Company stage indicators:** Job description tone, requirements, and expectations reveal culture

**Scoring Guidance:**

| Score | Interpretation | Characteristics |
|-------|----------------|-----------------|
| 10 | Exceptional fit | Work style, values, and communication approach strongly aligned; likely to thrive and elevate culture |
| 7-9 | Strong fit | Good alignment across most cultural dimensions; minor differences manageable |
| 4-6 | Moderate fit | Some alignment, some adaptation needed; cultural differences present but not disqualifying |
| 1-3 | Poor fit | Significant values or style misalignment; likely friction or disengagement |

**Valuing Non-Traditional Backgrounds:**

Self-taught professionals and entrepreneurs often bring cultural strengths:
- **Self-motivation:** Driven by intrinsic learning, not external structure
- **Ownership mentality:** Bias toward taking initiative vs. waiting for direction
- **Resourcefulness:** Solving problems with constraints
- **Adaptability:** Comfort with ambiguity and change

**Common Pitfalls This Dimension Corrects:**
- **"Culture fit" as conformity:** True fit is value alignment, not demographic similarity
- **Bias toward pedigree:** Elite university or big-name company experience ≠ cultural fit
- **Overweighting style similarity:** Diversity of thought requires diverse backgrounds

**Example Scenario:**

*Job description tone:* "Fast-paced startup seeking self-starters comfortable with ambiguity. We value shipping over perfection and learning from iteration."

*Candidate A:* 10 years at large enterprise, emphasizes "following established processes," "working within defined frameworks" → Score: 4 (style mismatch with startup velocity)

*Candidate B:* Built indie SaaS projects on weekends, writes about "bias toward action," describes "launching MVPs to validate hypotheses" → Score: 9 (entrepreneurial style aligns with startup culture)

---

### 3.6 Career Trajectory

**Definition:** Career Trajectory evaluates the pattern and velocity of a candidate's professional growth, assessing whether they are on an upward path, stagnant, or declining.

**Rationale:** This dimension answers "Where is this person going?" A candidate on a steep growth trajectory will continue learning and expanding impact. A stagnant career suggests limited future growth potential. Trajectory predicts future performance better than current state.

**Inputs Considered:**
- **Scope expansion:** Increasing responsibilities, team size, or technical complexity over time
- **Skill acquisition:** Evidence of continuous learning and adding new capabilities
- **Impact growth:** Measurable increases in value delivered (revenue, users, scale, etc.)
- **Role progression:** Promotions, title changes, leadership opportunities
- **Learning velocity:** Speed of mastering new domains or technologies
- **Non-linear growth signals:** Career changes that represent upward moves, not lateral drift

**Scoring Guidance:**

| Score | Interpretation | Characteristics |
|-------|----------------|-----------------|
| 10 | Rocket ship trajectory | Rapid growth; constantly learning; expanding scope significantly; accelerating impact |
| 7-9 | Strong trajectory | Steady progression; skills expanding regularly; clear upward movement |
| 4-6 | Stable trajectory | Incremental growth; slow but consistent skill development |
| 1-3 | Stagnant or declining | No visible growth; same role/skills for extended period; declining scope of work |

**Philosophy on Non-Linear Careers:**

Career changes, lateral moves, or gaps **do not indicate** low trajectory if they represent strategic growth:
- Developer → Engineering Manager → Startup Founder = strong trajectory (expanding scope)
- Consultant → In-house Engineer = may signal strong trajectory (choosing depth over breadth)
- 2-year gap building open source project = positive trajectory signal (continuous learning)

**Common Pitfalls This Dimension Corrects:**
- **Tenure bias:** 10 years doing the same work ≠ strong trajectory
- **Title inflation:** Promotions without scope increase are recognized
- **Gap penalties:** Career gaps for learning, entrepreneurship, or personal projects are valued positively
- **Industry change bias:** Switching domains can signal growth, not instability

**Example Scenario:**

*Candidate A:* 12 years as "Software Engineer" at same company, similar responsibilities throughout, technology stack unchanged → Score: 3 (stagnant, no growth visible)

*Candidate B:*
- Years 1-2: Junior Developer
- Years 3-4: Mid-level, took on mentoring
- Years 5-6: Senior, led architecture redesign
- Year 7: Gap (built open-source project that reached 2k GitHub stars)
- Year 8-present: Engineering Lead at new company

→ Score: 9 (strong acceleration, continuous learning, expanding impact)

---

### 3.7 Compensation Alignment

**Definition:** Compensation Alignment assesses the likelihood that the candidate's salary expectations will align with the employer's budget for the role, based on experience level, background, and market signals.

**Rationale:** This dimension answers "Will compensation be feasible?" High scores in all other dimensions are irrelevant if compensation expectations are double the budgeted range. This dimension prevents wasted time on candidates with misaligned expectations.

**Inputs Considered:**
- **Seniority level and titles:** Senior/Principal/Staff roles command higher compensation
- **Company background:** FAANG/Big Tech, enterprise, startup, or small company experience sets expectations
- **Role type:** Consultant/freelance backgrounds often have premium rate expectations
- **Career stage:** Career changers and bootcamp graduates typically have more flexible expectations
- **Geographic location:** Cost of living in candidate's location
- **Progression pattern:** Consistent level changes vs. large jumps

**Scoring Guidance:**

| Score | Interpretation | Characteristics |
|-------|----------------|-----------------|
| 10 | Strong alignment | Expectations likely match budget; signals suggest realistic comp requirements |
| 7-9 | Good alignment | Negotiable range; minor gap possible but addressable |
| 4-6 | Moderate concern | Potential mismatch but not disqualifying; negotiation required |
| 1-3 | Significant mismatch | Expectations likely far exceed budget or candidate significantly underqualified for comp level |

**Compensation Expectation Signals:**

**Higher Expectations (reduce score):**
- FAANG/Big Tech background (typically $300-500k+ total comp expectations)
- Senior/Principal/Staff/C-level titles
- Consultant or freelance background (premium hourly rates)
- High cost of living location (SF, NYC, London)
- Multiple startups with equity focus

**Moderate/Flexible Expectations (increase score):**
- Transitioning from non-tech to tech roles
- Career switcher or bootcamp graduate
- Startup-to-startup moves (understands equity/cash trade-offs)
- Seeking remote work (may accept geographic arbitrage)
- Consistent level progression (predictable expectations)

**Common Pitfalls This Dimension Corrects:**
- **Waste reduction:** Avoids lengthy processes with candidates who will decline due to comp
- **False negatives:** Recognizes that non-traditional candidates often have lower comp expectations despite strong capability
- **Credential premium:** Doesn't assume elite backgrounds automatically demand premium compensation

**Example Scenario:**

*Role:* Senior Software Engineer at series A startup ($150k-180k range)

*Candidate A:* Staff Engineer at Google, L6 level, SF-based → Score: 2 (current comp likely $400k+ total, expectations far exceed budget)

*Candidate B:* Senior Engineer at mid-stage startup, previously at series B company, mentions "interested in early-stage equity opportunity" → Score: 8 (signals flexibility, understands startup comp structure)

---

## 4. Composite Scoring

### 4.1 Combining Dimensions

The seven dimensions combine into a 0-100 aggregate score through a **weighted average** that reflects the relative importance of each dimension for the role. Each dimension is scored 1-10; these scores are weighted and scaled to produce the final composite.

**Composite Score Formula (Conceptual):**

```
Aggregate Score = (
  Qualification × W₁ +
  Capability × W₂ +
  Situational × W₃ +
  Reward × W₄ +
  Culture × W₅ +
  Trajectory × W₆ +
  Compensation × W₇
) × 10
```

Where W₁ through W₇ are role-dependent weights that sum to 1.0.

**Note on Weights:** Exact weight values are implementation-specific and proprietary to individual systems. The framework specifies that weights should be role-dependent and account for strategic priorities.

### 4.2 Role-Based Weighting Philosophy

Dimension importance varies by role type:

**For Mission-Critical Technical Roles:**
- Higher weight on **Capability Confidence** (must execute flawlessly)
- Moderate weight on **Situational Stability** (retention important but can be managed)
- Lower weight on **Compensation Alignment** (accept higher comp for critical capability)

**For High-Growth Roles:**
- Higher weight on **Reward Potential** (seeking transformational impact)
- Higher weight on **Career Trajectory** (need continuous learners)
- Lower weight on **Situational Stability** (accept some risk for high upside)

**For Executive Roles:**
- Higher weight on **Capability Confidence** (proven execution required)
- Higher weight on **Reward Potential** (hiring for multiplicative impact)
- Lower weight on **Compensation Alignment** (accept premium comp for top talent)

**For Volume Hiring:**
- Higher weight on **Qualification Match** (need clear fit)
- Higher weight on **Compensation Alignment** (must stay in budget)
- Higher weight on **Situational Stability** (minimize churn)

**General Principle:** Qualification and Capability typically carry highest weight for most roles, followed by role-specific strategic priorities.

### 4.3 Score Interpretation Guidelines

| Aggregate Score | Interpretation | Action |
|-----------------|----------------|--------|
| 90-100 | Exceptional match | Strong yes—prioritize interview, move fast |
| 75-89 | Strong match | Yes—schedule interview, likely good fit |
| 60-74 | Moderate match | Maybe—interview if capacity allows, context-dependent |
| 45-59 | Weak match | Likely no—only proceed if unique circumstances |
| 0-44 | Poor match | No—significant gaps or misalignment |

**Context Matters:** A 65 aggregate score may be a "yes" for a hard-to-fill niche role but a "no" for a competitive position with many applicants.

---

## 5. Hidden Gem Detection

### 5.1 Definition of a Hidden Gem

A **hidden gem** is a candidate who:
1. Possesses strong capability and high potential to succeed in the role
2. Would be systematically rejected by traditional keyword-based ATS systems
3. Has a non-traditional background that lacks conventional signals (specific degree, linear career, target company experience, keyword density)

Hidden gems typically come from:
- **Self-taught backgrounds:** No formal degree but strong portfolio and fundamentals
- **Career changers:** Transitioning from another domain with transferable skills
- **Entrepreneurs:** Business ownership experience, including "failed" ventures
- **Non-linear careers:** Gaps for learning, side projects, or personal circumstances
- **Underrepresented groups:** Lack access to traditional credential pipelines

### 5.2 Why Traditional Systems Miss Them

Traditional ATS systems filter on:
- **Keyword density:** Self-taught candidates may lack buzzword saturation
- **Degree requirements:** "BS in Computer Science required" rejects strong self-taught talent
- **Company name matching:** "Experience at Google, Amazon, or similar" excludes startup backgrounds
- **Linear progression:** Any gap or lateral move triggers rejection
- **Exact skill matching:** Transferable skills from adjacent domains ignored

Result: Exceptional talent with high potential is never seen by human recruiters.

### 5.3 How 7D Identifies Hidden Gems (Conceptual)

The framework detects hidden gems through:

1. **Capability evidence over credentials:** Portfolio quality matters more than degree source
2. **Trajectory analysis:** Rapid skill acquisition signals potential despite short tenure
3. **Bias correction rules:** Entrepreneurship gaps scored positively, not negatively
4. **Transferable skill recognition:** Experience from adjacent domains valued appropriately
5. **Reward potential weighting:** Non-traditional backgrounds often bring fresh perspectives

**Hidden Gem Signals:**
- High **Capability Confidence** (strong evidence) despite low **Qualification Match** (lacks keywords)
- High **Reward Potential** (unique value) with non-linear career
- High **Career Trajectory** (rapid growth) despite short experience
- Evidence of self-directed learning and problem-solving
- Portfolio contradicts credential gaps

### 5.4 Example Hidden Gem Profiles

**Profile 1: Self-Taught Developer**

*Background:* High school education, 4 years self-taught programming, built 3 production SaaS applications used by 5,000+ users, active open-source contributor

*Why traditional ATS rejects:* No CS degree, lacks "5+ years professional experience"

*Why 7D flags as hidden gem:*
- Capability Confidence: 9 (portfolio demonstrates strong fundamentals)
- Reward Potential: 8 (self-motivation, ownership, proven builder)
- Compensation Alignment: 9 (typically more flexible than traditional candidates)
- Qualification Match: 6 (transferable skills present but non-traditional path)

**Profile 2: Entrepreneur → Employee**

*Background:* Built startup for 3 years (reached $10k MRR but shut down), now seeking employment; MBA background but technical co-founder role

*Why traditional ATS rejects:* 3-year employment gap, "failed" business, lacks traditional technical role titles

*Why 7D flags as hidden gem:*
- Reward Potential: 9 (entrepreneurial drive, understands business context)
- Capability Confidence: 7 (technical execution demonstrated)
- Career Trajectory: 8 (rapid skill acquisition in technical domain)
- Situational Stability: 8 (motivated for stability after startup journey)

**Profile 3: Career Changer**

*Background:* 8 years as teacher, completed coding bootcamp 6 months ago, built portfolio of 5 web applications, strong communication skills

*Why traditional ATS rejects:* "3+ years software development experience required"

*Why 7D flags as hidden gem:*
- Capability Confidence: 7 (portfolio shows strong fundamentals, rapid learning)
- Career Trajectory: 9 (steep learning curve, high velocity)
- Culture Fit: 8 (teaching background = strong communication, mentorship)
- Compensation Alignment: 9 (realistic expectations as career changer)
- Reward Potential: 7 (diverse background, fresh perspective)

---

## 6. Bias Mitigation

The 7D Framework includes explicit bias correction mechanisms to counter systematic biases present in traditional screening:

### 6.1 Credential Bias Correction

**Traditional bias:** Candidates from elite universities or with advanced degrees automatically score higher.

**7D correction:**
- Capability Confidence emphasizes **evidence depth** over credential source
- A self-taught developer with strong portfolio may score 9/10 in Capability despite lacking degree
- Formal education is one signal among many, not a gating criterion

**Principle:** "10 years self-taught experience building production systems" > "2 years with CS degree from top university" when evidence supports it.

### 6.2 Career Gap Interpretation

**Traditional bias:** Any employment gap is a negative signal.

**7D correction:**
- Gaps for **entrepreneurship, side projects, or learning** are positive signals in Reward Potential and Career Trajectory
- Gaps for personal circumstances are neutral (not penalized)
- Framework asks "What did they learn/build during this period?" not "Why is there a gap?"

**Principle:** A 2-year gap spent building an open-source project demonstrates stronger capability than 2 years of routine work.

### 6.3 Non-Linear Career Paths

**Traditional bias:** Lateral moves or domain changes indicate instability or poor performance.

**7D correction:**
- Career changes evaluated through **Career Trajectory** lens: Is this expanding skills/scope?
- Domain switching can signal adaptability and learning velocity (positive)
- Lateral moves to learn new technologies scored positively if growth is evident

**Principle:** Developer → PM → Founder shows expanding scope (strong trajectory), not instability.

### 6.4 Transferable Skills Recognition

**Traditional bias:** Only exact skill matches count; adjacent domain experience ignored.

**7D correction:**
- **Qualification Match** and **Capability Confidence** explicitly evaluate transferable skills
- Experience solving similar problems in different technology stacks is valued
- Fundamentals and problem-solving approaches matter more than specific tools

**Principle:** A strong backend engineer in Python can transfer to Go with short ramp time.

---

## 7. Implementation Considerations

### 7.1 Manual Application (Recruiters Without Automation)

Recruiters can apply the framework manually using a structured worksheet:

**Process:**
1. Read job description and identify key requirements
2. Review candidate CV/resume
3. Score each dimension 1-10 using the guidance tables in Section 3
4. Calculate weighted average (use standard weights or define custom weights for role)
5. Document strengths, concerns, and recommendation
6. Flag hidden gem potential if criteria met

**Time estimate:** 10-15 minutes per candidate for experienced recruiters

**Calibration:** Teams should calibrate scoring through:
- Reviewing scored candidates as a group
- Discussing score rationale
- Adjusting for consistency
- Establishing team-specific anchors for each dimension

### 7.2 Software Integration (Developers)

Developers implementing automated 7D evaluation should:

**Input Requirements:**
- Job description (text)
- Candidate CV/resume (text or structured data)
- Optional: Company context, compensation range, location requirements

**Processing Pipeline:**
1. Extract job requirements and candidate qualifications (NLP/AI extraction)
2. Evaluate each dimension independently using scoring criteria
3. Apply bias correction rules
4. Calculate weighted aggregate score
5. Generate explanation (strengths, concerns, recommendation)
6. Flag hidden gems based on signal patterns

**Output Format:**
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
  "hidden_gem": {
    "is_hidden_gem": true,
    "reasoning": "Self-taught background with strong portfolio..."
  },
  "strengths": [...],
  "concerns": [...]
}
```

**Technology Considerations:**
- Large Language Models (LLMs) are well-suited for implementing 7D evaluation due to their ability to understand context and nuance
- Traditional ML approaches can be used but require extensive feature engineering
- Hybrid approaches (ML for extraction + rules for scoring) are viable

### 7.3 Calibration Guidance

Achieving consistent scoring requires calibration:

**For Teams:**
1. Score 20-30 test candidates individually
2. Compare scores across team members
3. Discuss outliers and reasoning
4. Establish shared examples for each score level (anchoring)
5. Re-score periodically to maintain consistency

**For Automated Systems:**
1. Human-label evaluation set (100+ candidates)
2. Compare automated scores to human expert scores
3. Tune weights and thresholds to minimize divergence
4. Monitor score distribution over time
5. Collect feedback on hire quality to validate predictive power

### 7.4 Quality Assurance

Validation that the framework is working correctly:

**Process Metrics:**
- **Score distribution:** Should see bell curve, not all high/low scores
- **Hidden gem detection rate:** Should identify 10-20% of candidates as hidden gems
- **Dimension variance:** Scores should vary across dimensions (if all 7 dimensions score identically, evaluation is too shallow)

**Outcome Metrics:**
- **Interview-to-offer rate:** Should increase (better pre-screening)
- **Offer acceptance rate:** Should increase (better situational fit assessment)
- **90-day retention:** Should increase (better cultural fit)
- **Performance ratings:** Should correlate with aggregate scores

---

## 8. Glossary

**Aggregate Score:** The 0-100 composite score derived from weighted combination of the seven dimension scores.

**Capability Confidence:** Dimension measuring certainty that a candidate can perform core job functions based on evidence.

**Career Trajectory:** Dimension evaluating growth pattern and learning velocity over time.

**Compensation Alignment:** Dimension assessing likelihood of salary expectation alignment with budget.

**Cultural Fit:** Dimension measuring alignment between candidate's work style/values and organization culture.

**Dimension:** One of the seven independent evaluation criteria (Qualification, Capability, Situational, Reward, Culture, Trajectory, Compensation).

**Hidden Gem:** A candidate with strong capability and potential who would be rejected by keyword-based systems due to non-traditional background.

**Qualification Match:** Dimension measuring how well skills/experience align with job requirements.

**Reward Potential:** Dimension assessing the upside value if the hire succeeds.

**Situational Stability:** Dimension evaluating likelihood that candidate will join, stay, and be available.

**Transferable Skills:** Capabilities from adjacent domains that apply to the target role despite not being exact matches.

---

## Appendix A: Example Evaluations

See `examples/` directory for full evaluation samples:
- `example-senior-engineer.json` - Traditional strong candidate
- `example-hidden-gem-self-taught.json` - Hidden gem: self-taught developer
- `example-hidden-gem-career-changer.json` - Hidden gem: career changer
- `example-comparison.json` - Side-by-side comparison

---

## About

### Created By

**Tanova** (Pedersen Consulting)
Website: [https://tanova.ai](https://tanova.ai)

### Version History

- **v1.0.0** (2025-12-11): Initial public release

### License

This framework specification is licensed under **Creative Commons Attribution 4.0 International (CC BY 4.0)**.

You are free to:
- **Share:** Copy and redistribute the material
- **Adapt:** Build upon the framework for any purpose

Under the following terms:
- **Attribution:** You must give appropriate credit, provide a link to the license, and indicate if changes were made

See [LICENSE](LICENSE) file for full terms.

### Citation Format

If you reference this framework in research or publications, please cite:

> Tanova. (2025). *The 7D Candidate Evaluation Framework* (Version 1.0). Retrieved from https://tanova.ai/7d-framework

For software implementations, please include attribution in documentation:

> This system uses the 7D Candidate Evaluation Framework by Tanova (https://tanova.ai/7d-framework)

### Automated Evaluation

For production-ready automated 7D evaluation, visit [https://tanova.ai](https://tanova.ai).

### Contributing

Feedback and suggestions for future versions: [hello@tanova.ai](mailto:hello@tanova.ai)
