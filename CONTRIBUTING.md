# Contributing to Detection Engineering Repository

We welcome contributions from the security community! Here's how to contribute effectively.

## Detection Rule Standards

### Required Metadata
- **Title**: Clear, descriptive name
- **Description**: What the rule detects and why it's suspicious
- **Author**: Rule creator and contact info
- **Date**: Creation and last modification dates
- **MITRE ATT&CK**: Relevant tactic and technique IDs
- **Severity**: Critical, High, Medium, Low
- **Data Sources**: Required log sources and fields
- **False Positives**: Expected FP scenarios and mitigation strategies
- **Testing**: Validation methodology and test cases

### File Naming Convention
- Use descriptive names: `lateral_movement_rdp_suspicious_logon.yml`
- Include MITRE technique ID: `t1078_valid_accounts_unusual_time.yml`
- Use underscores and lowercase
- Version significant updates: `rule_name_v2.yml`

### Quality Checklist
- [ ] Rule syntax is valid for target platform
- [ ] Metadata is complete and accurate
- [ ] MITRE ATT&CK mapping is correct
- [ ] False positive analysis completed
- [ ] Testing methodology documented
- [ ] Peer review completed

## Submission Process

1. Fork the repository
2. Create a feature branch
3. Add your detection rule with complete metadata
4. Test the rule in your environment
5. Submit a pull request with detailed description
6. Address reviewer feedback

## Code of Conduct

- Be respectful and constructive
- Focus on improving detection capabilities
- Share knowledge and learn from others
- Maintain professional standards
