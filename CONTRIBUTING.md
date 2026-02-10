# Contributing to 7D Framework

Thank you for considering contributing to the 7D Candidate Evaluation Framework! This is a **community-driven project** and we welcome contributions from recruiters, HR professionals, developers, and anyone passionate about making hiring more transparent and fair.

---

## 🎯 How You Can Contribute

### 1. **Feedback & Real-World Experience**
- Share your experience using the framework in production
- Report what worked and what didn't
- Suggest improvements to dimension definitions
- Share calibration insights

### 2. **Examples & Case Studies**
- Contribute anonymized evaluation examples
- Document hidden gem discoveries
- Share bias mitigation results
- Compare outcomes with traditional ATS

### 3. **Domain-Specific Adaptations**
- Adapt dimension weights for specific industries (healthcare, finance, tech, etc.)
- Create specialized evaluation guides
- Develop role-specific weighting schemes

### 4. **Translations**
- Translate framework to other languages
- Adapt cultural examples appropriately
- Maintain scoring guidance principles

### 5. **Research & Validation**
- Academic research using the framework
- Comparative studies with other methodologies
- Bias audits and fairness analysis
- Longitudinal outcome tracking

### 6. **Documentation Improvements**
- README enhancements
- Implementation guide updates
- Tutorial creation
- FAQ additions

---

## 📋 Contribution Guidelines

### For Feedback

1. Open a [GitHub Issue](https://github.com/tanova-ai/7d-framework/issues) with tag `[feedback]`
2. Describe your use case (company size, industry, role types)
3. Share what worked and what didn't (be specific)
4. Suggest concrete improvements with reasoning

**Example good feedback:**
> **Use Case:** Tech startup, hiring 5 engineers/year
> **What Worked:** Hidden gem detection found 2 strong candidates we'd have rejected
> **What Didn't:** Compensation Alignment scoring was too simplistic for equity-heavy offers
> **Suggestion:** Add equity/stock option considerations to Dimension 7

### For Examples

**Requirements:**
1. **Anonymize all personal information** (name, company, contact details)
2. Follow the JSON schema format in `schema.json`
3. Include both traditional candidates and hidden gems
4. Document reasoning for each dimension score
5. Include final hiring outcome (if known)

**Directory:** Place examples in `examples/evaluations/`

**Filename format:** `example-[role]-[type]-[outcome].json`

Example: `example-senior-engineer-hidden-gem-hired.json`

### For Translations

**Requirements:**
1. Maintain exact meaning of dimension definitions
2. Adapt cultural examples appropriately (job titles, industries, education systems)
3. Preserve scoring guidance principles (1-10 scale, weighting logic)
4. Document any necessary cultural adaptations in comments

**Directory:** Create `translations/[language-code]/`

Example: `translations/es/` for Spanish

### For Research

If you're conducting research using the 7D Framework:

1. Email us at [hello@tanova.ai](mailto:hello@tanova.ai) to let us know
2. We can provide additional validation data if helpful
3. We're happy to review drafts and provide feedback
4. Please cite the framework appropriately (see README)

---

## 🚀 Pull Request Process

### 1. Fork the Repository

```bash
git clone https://github.com/tanova-ai/7d-framework.git
cd 7d-framework
git checkout -b feature/your-contribution
```

### 2. Make Your Changes

- Follow existing code/documentation style
- Validate JSON against schema if applicable
- Test examples to ensure they work

### 3. Commit with Clear Messages

```bash
git add .
git commit -m "Add: Example of hidden gem software engineer evaluation"
```

**Commit message format:**
- `Add:` New content (examples, documentation)
- `Fix:` Bug fixes, typos, broken links
- `Update:` Improvements to existing content
- `Docs:` Documentation-only changes

### 4. Submit Pull Request

- Provide clear description of changes
- Reference any related issues
- Explain reasoning for improvements
- Include test cases if applicable

---

## ✅ Quality Standards

### For Code/Schema Changes:
- Must validate against existing schemas
- Maintain backward compatibility (unless major version bump)
- Include tests or validation examples

### For Documentation:
- Clear, concise writing
- Real-world examples when possible
- Proper markdown formatting
- All links tested and working

### For Examples:
- Complete dimension scores (all 7 dimensions)
- Clear reasoning for each score
- Anonymized personal information
- Realistic scenarios

---

## ❓ Questions & Support

### Before Opening an Issue:
1. Check [existing issues](https://github.com/tanova-ai/7d-framework/issues)
2. Review [SPECIFICATION.md](./SPECIFICATION.md) for detailed guidance
3. Check [examples/](./examples/) for similar use cases

### How to Ask Questions:
- **GitHub Issues:** For bugs, feature requests, or specific problems
- **GitHub Discussions:** For open-ended questions or general discussion
- **Email:** [hello@tanova.ai](mailto:hello@tanova.ai) for private inquiries

---

## 📜 Code of Conduct

### Our Commitment

We're committed to providing a welcoming, inclusive, and harassment-free experience for everyone.

### Expected Behavior

- **Be respectful** of different viewpoints and experiences
- **Be constructive** in feedback and criticism
- **Be collaborative** and help others learn
- **Be professional** in all interactions

### Unacceptable Behavior

- Harassment, discriminatory language, or personal attacks
- Trolling, insulting comments, or political attacks
- Publishing others' private information without consent
- Other conduct inappropriate in a professional setting

### Enforcement

Violations may result in removal of comments, temporary ban, or permanent ban from the project.

Report violations to: [hello@tanova.ai](mailto:hello@tanova.ai)

---

## 🏆 Recognition

### Contributors

We maintain a list of contributors in:
- README.md (significant contributions)
- CHANGELOG.md (per-version contributions)
- This CONTRIBUTING.md file

### Types of Recognition

- **Code/Schema Contributors:** Listed in CHANGELOG with attribution
- **Example Contributors:** Anonymized attribution in example metadata
- **Documentation Contributors:** Listed in README credits
- **Research Contributors:** Cited in validation studies

---

## 📄 License

By contributing to this project, you agree that your contributions will be licensed under the same **Creative Commons Attribution 4.0 International (CC BY 4.0)** license as the framework.

This means:
- ✅ Your contribution can be used freely (including commercially)
- ✅ You retain copyright to your contribution
- ✅ Attribution will be given to you
- ✅ You grant others the right to use your contribution under CC BY 4.0

---

## 🙏 Thank You!

Every contribution helps make hiring more transparent and fair. Whether you're fixing a typo, sharing an example, or conducting research—your input is valued.

**Questions?** Email [hello@tanova.ai](mailto:hello@tanova.ai)

**Want to discuss ideas?** Open a [GitHub Discussion](https://github.com/tanova-ai/7d-framework/discussions)

---

**Project maintained by [Tanova.ai](https://tanova.ai)**
