# 7D Candidate Evaluation Framework

The **7D Framework** is an open methodology for multi-dimensional candidate evaluation, created by [Tanova](https://tanova.ai).

Traditional Applicant Tracking Systems (ATS) filter candidates using keyword matching and credential verification, systematically excluding exceptional self-taught professionals, career changers, and entrepreneurs. The 7D Framework provides a structured approach to evaluate candidates across seven independent dimensions, identifying both conventional strong matches and "hidden gems" that traditional systems miss.

---

## Quick Overview

The framework evaluates candidates across **seven dimensions**, each scored 1-10:

1. **Qualification Match** - How well skills/experience align with requirements
2. **Capability Confidence** - Degree of certainty they can perform the role
3. **Situational Stability** - Likelihood they'll join, stay, and be available
4. **Reward Potential** - Upside value if this hire succeeds
5. **Cultural Fit** - Alignment with work style and values
6. **Career Trajectory** - Growth pattern and learning velocity
7. **Compensation Alignment** - Salary expectation alignment likelihood

These combine into a **0-100 aggregate score** using role-dependent weighting.

---

## Why 7D?

**The Problem:**

Keyword-based screening systematically rejects candidates who:
- Are self-taught without formal degrees
- Changed careers with transferable skills
- Have entrepreneurial experience ("employment gaps")
- Lack buzzword density despite strong capability

**The Solution:**

Multi-dimensional evaluation that:
- Values **evidence over credentials**
- Recognizes **transferable skills** from adjacent domains
- Scores **entrepreneurship positively** (failed ventures = high learning)
- Detects **hidden gems** with high potential but non-traditional backgrounds

**The Result:**

- Find exceptional talent others overlook
- Reduce bias from credential-based filtering
- Make data-driven hiring decisions
- Improve diversity through non-traditional path recognition

---

## What's Here

- **[SPECIFICATION.md](SPECIFICATION.md)** - Complete framework documentation
  - Detailed dimension definitions
  - Scoring guidance and examples
  - Hidden gem detection methodology
  - Bias mitigation approach

- **[schema.yaml](schema.yaml) / [schema.json](schema.json)** - Machine-readable schemas
  - Dimension specifications
  - Output format definitions
  - Validation criteria

- **[IMPLEMENTATION_GUIDE.md](IMPLEMENTATION_GUIDE.md)** - How to apply the framework
  - Manual evaluation worksheets for recruiters
  - Software integration guide for developers
  - Calibration procedures
  - Quality assurance metrics

- **[examples/](examples/)** - Sample evaluations
  - Traditional strong candidate
  - Hidden gem: self-taught developer
  - Hidden gem: career changer
  - Comparison scenarios

---

## Using This Framework

### For Recruiters

Use the manual evaluation worksheet in the [Implementation Guide](IMPLEMENTATION_GUIDE.md#for-recruiters-manual-application):

1. Read job description and candidate CV
2. Score each dimension 1-10 using scoring guidance
3. Calculate weighted average
4. Flag hidden gems if criteria met
5. Document strengths, concerns, recommendation

**Time:** 10-15 minutes per candidate after calibration

### For Developers

Implement automated 7D evaluation:

**Input:**
```json
{
  "job_description": "Full text...",
  "candidate_cv": "Full text..."
}
```

**Output:**
```json
{
  "scores": {
    "qualification": 7,
    "capability_confidence": 8,
    ...
  },
  "aggregate_score": 77,
  "recommendation": "yes",
  "hidden_gem": {
    "is_hidden_gem": true,
    "reasoning": "..."
  },
  "strengths": [...],
  "concerns": [...]
}
```

See [Implementation Guide - For Developers](IMPLEMENTATION_GUIDE.md#for-developers-software-integration) for architecture, pseudocode, and API design.

### For Researchers

The framework is published under CC BY 4.0. You may:
- Reference in academic work
- Build upon for research
- Adapt for specific domains
- Compare against other methodologies

Please cite as:

> Tanova. (2025). *The 7D Candidate Evaluation Framework* (Version 1.0).
> Retrieved from https://tanova.ai/7d-framework

---

## Key Concepts

### Hidden Gems

**Definition:** Candidates with strong capability and high potential who would be rejected by keyword-based systems.

**Why Systems Miss Them:**
- No formal degree → Auto-reject
- Employment gaps → Auto-reject
- Keyword density too low → Auto-reject
- Career transitions → "Job hopper"

**Why They Succeed:**
- Self-motivation and ownership
- Rapid learning velocity
- Fresh perspectives
- High loyalty (grateful for opportunity)
- Often more cost-effective

**Detection Signals:**
- High Capability (7+) + Low Qualification (≤6)
- High Reward (8+) + Non-linear career
- High Trajectory (8+) + Short experience
- Portfolio contradicts credential gaps

### Bias Mitigation

The framework corrects systematic biases:

| Traditional Bias | 7D Correction |
|------------------|---------------|
| Elite degrees score higher | Evidence depth matters, not credential source |
| Employment gaps are negative | Gaps for learning/entrepreneurship are positive |
| Career changes = instability | Evaluated for skill expansion and growth |
| Only exact skill matches count | Transferable skills from adjacent domains valued |

### Role-Based Weighting

Dimension importance varies by role:

- **Technical roles:** Higher Capability weight
- **Volume hiring:** Higher Compensation + Situational weights
- **Leadership roles:** Higher Reward + Capability weights
- **Mission-critical:** Higher Capability, lower Compensation weight

---

## Examples

### Traditional Strong Candidate

- BS Computer Science, 8 years experience
- Clear skill match, proven track record
- **Aggregate:** 82/100
- **Hidden Gem:** No
- **Would ATS pass?** Yes

### Hidden Gem: Self-Taught Developer

- High school education, 6 years self-taught
- Portfolio: 3 production SaaS apps, 8k+ users
- Strong fundamentals, rapid learning
- **Aggregate:** 80/100
- **Hidden Gem:** Yes
- **Would ATS pass?** No (auto-reject on degree requirement)

See [examples/](examples/) for full evaluations.

---

## Automated Evaluation

For production-ready automated 7D evaluation with AI-powered scoring:

**Visit [https://tanova.ai](https://tanova.ai)**

Features:
- 30-90 second evaluation time
- Multi-language support
- Hidden gem detection
- Interview question generation
- API access

---

## License

This framework specification is licensed under **Creative Commons Attribution 4.0 International (CC BY 4.0)**.

✓ Share and adapt freely
✓ Use commercially
✓ Build software implementations
✗ Must provide attribution

See [LICENSE](LICENSE) for full terms.

---

## Citation

**Academic/Research:**
```
Tanova. (2025). The 7D Candidate Evaluation Framework (Version 1.0).
Retrieved from https://tanova.ai/7d-framework
```

**Software Documentation:**
```
This system uses the 7D Candidate Evaluation Framework by Tanova
https://tanova.ai/7d-framework
```

---

## Contributing

Feedback and suggestions for future versions: [hello@tanova.ai](mailto:hello@tanova.ai)

---

## About Tanova

**Tanova** (by Pedersen Consulting) created the 7D Framework to address systematic bias in AI recruitment systems. Our mission is to help organizations find exceptional talent regardless of background.

- Website: [https://tanova.ai](https://tanova.ai)
- Framework Docs: [https://tanova.ai/7d-framework](https://tanova.ai/7d-framework)
- Contact: [hello@tanova.ai](mailto:hello@tanova.ai)

---

## Version

**Current Version:** 1.0.0
**Release Date:** 2025-12-11
**Changelog:** [CHANGELOG.md](CHANGELOG.md)
