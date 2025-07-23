# Rule Writing Standards

## Metadata Standards

### Required Fields
- **title**: Human-readable rule name
- **id**: Unique identifier (UUID recommended)
- **description**: Clear explanation of what is detected
- **author**: Rule creator(s)
- **date**: Creation date (YYYY/MM/DD)
- **modified**: Last modification date
- **status**: experimental, testing, stable, deprecated
- **level**: critical, high, medium, low, informational

### MITRE ATT&CK Mapping
- **tactics**: Primary tactic (e.g., execution, persistence)
- **techniques**: Specific technique ID (e.g., T1059.001)
- **subtechniques**: When applicable

### Data Source Requirements
- **logsource**: Specify category, product, service
- **fields**: Required log fields
- **volume**: Expected data volume impact

## Naming Conventions

### File Names
- Use descriptive, lowercase names with underscores
- Include technique ID when applicable: `t1055_process_injection_hollow.yml`
- Group related rules: `lateral_movement_rdp_*`
- Version significant changes: `rule_name_v2.yml`

### Rule Titles
- Start with technique category: "Lateral Movement via RDP"
- Be specific: "Suspicious PowerShell Encoded Command"
- Avoid generic terms: Use "Process Injection" not "Suspicious Activity"

## Logic Standards

### Detection Logic
- Use positive logic when possible (detect what you want vs. exclude what you don't)
- Implement time windows for correlation rules
- Consider data normalization requirements
- Include confidence scoring when possible

### False Positive Handling
- Document known false positive scenarios
- Provide exclusion criteria
- Include tuning recommendations
- Specify acceptable FP rates

## Quality Gates

### Before Submission
- [ ] Syntax validation passes
- [ ] Metadata is complete
- [ ] Testing completed with results documented
- [ ] False positive analysis completed
- [ ] Performance impact assessed
- [ ] Peer review completed

### Review Criteria
- Technical accuracy
- Business value
- Maintainability
- Performance impact
- Documentation quality
