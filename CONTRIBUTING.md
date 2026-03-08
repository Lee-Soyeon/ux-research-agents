# Contributing to UX Research Agents

Thank you for your interest in contributing. This project aims to make rigorous UX research methodology accessible to all product teams through AI-powered analysis tools.

## 1. How to Contribute

### 1.1 Types of Contributions

- **Methodology improvements**: Enhancements to the analysis frameworks, additional research methodologies, or refinements to existing stages
- **New agent definitions**: Agent files for other types of UX research (e.g., diary studies, card sorting analysis, A/B test interpretation)
- **Prompt improvements**: Better prompts for transcript analysis, more robust tagging logic
- **Templates**: New templates for common UX research activities
- **Examples**: Sample transcripts, sample analysis outputs, or tutorial walkthroughs
- **Bug fixes**: Corrections to methodology descriptions, formatting issues, or broken references
- **Documentation**: Improving README, adding usage guides, or translating content

### 1.2 What We Are Not Looking For

- Product-specific customizations (this project is intentionally generic)
- Proprietary methodology that cannot be openly attributed
- Changes that reduce methodological rigor for the sake of brevity

## 2. Getting Started

### 2.1 Fork and Clone

```bash
git clone https://github.com/YOUR-USERNAME/ux-research-agents.git
cd ux-research-agents
```

### 2.2 Branch Naming

Create a branch from `main` with a descriptive name:

```bash
git checkout -b feature/add-diary-study-agent
git checkout -b fix/empathy-map-stage-clarification
git checkout -b docs/add-cross-analysis-example
```

## 3. Contribution Guidelines

### 3.1 Writing Style

- All content must be in **English**
- No emojis in any files
- Use hierarchical numbering (1. 1.1 1.1.1) for document structure
- Keep formatting clean and professional
- Cite methodology sources (e.g., "Reference: NNG 'Empathy Mapping: The First Step in Design Thinking'")

### 3.2 Agent Files

Agent files in `agents/` must:
- Include YAML frontmatter with `name`, `description`, `tools`, and `model` fields
- Work as drop-in Claude Code custom agents
- Use relative paths or placeholder paths (not absolute paths)
- Maintain separation between methodology and product-specific content
- Preserve all framework references and citations

### 3.3 Prompt Files

Prompt files in `prompts/` must:
- Be standalone (usable by copy-pasting into any LLM)
- Include clear usage instructions
- Not assume any specific tool or platform

### 3.4 Templates

Templates in `templates/` must:
- Be generic enough to apply to any product
- Include clear placeholder markers for customization
- Explain the purpose of each section

### 3.5 Examples

Examples in `examples/` must:
- Use fictional but realistic data
- Not reference any real product, company, or person
- Be detailed enough to demonstrate the tools effectively

## 4. Pull Request Process

### 4.1 Before Submitting

- Ensure your changes follow the writing style guidelines above
- Verify that agent files have valid YAML frontmatter
- Check that no product-specific content, real names, or proprietary information is included
- Test agent files if possible (run them against the sample transcript)

### 4.2 PR Description

Include:
1. **What**: Brief description of the change
2. **Why**: Motivation or problem being solved
3. **Methodology reference**: If adding or modifying a research framework, cite the source

### 4.3 Review Process

- PRs will be reviewed for methodological accuracy, writing quality, and generalizability
- Expect feedback within one week
- Small fixes may be merged quickly; methodology changes will receive more thorough review

## 5. Code of Conduct

- Be respectful and constructive in all interactions
- Focus feedback on the content, not the contributor
- Acknowledge that UX research methodologies can be applied in different valid ways
- Credit original sources and prior work

## 6. Questions

If you have questions about contributing, open an issue with the "question" label. We are happy to help.
