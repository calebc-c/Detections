# Detection Engineering Guide

This guide provides best practices for creating, testing, and maintaining detection rules across multiple security platforms.

## Detection Rule Lifecycle

### 1. Planning Phase
- Identify threat or technique to detect
- Map to MITRE ATT&CK framework
- Determine required data sources
- Define success criteria

### 2. Development Phase
- Write initial rule logic
- Include comprehensive metadata
- Document data source requirements
- Consider performance implications

### 3. Testing Phase
- Validate rule syntax
- Test with known good/bad data
- Assess false positive rate
- Performance impact analysis

### 4. Deployment Phase
- Deploy to test environment first
- Monitor for false positives
- Adjust sensitivity if needed
- Deploy to production

### 5. Maintenance Phase
- Regular effectiveness reviews
- Update for new attack variants
- Optimize for performance
- Archive obsolete rules

## Rule Writing Best Practices

### Sigma Rules
```yaml
title: Suspicious PowerShell Command Line
id: [unique-guid]
status: experimental
description: Detects suspicious PowerShell command line parameters
author: Your Name
date: 2025/01/01
modified: 2025/01/01
tags:
  - attack.execution
  - attack.t1059.001
logsource:
  category: process_creation
  product: windows
detection:
  selection:
    Image|endswith: '\powershell.exe'
    CommandLine|contains:
      - '-EncodedCommand'
      - '-WindowStyle Hidden'
  condition: selection
falsepositives:
  - Legitimate administrative scripts
level: medium
```

### Splunk SPL
```spl
| search index=windows EventCode=4688
| where match(NewProcessName, "(?i)powershell\.exe$")
| where match(CommandLine, "(?i)(-encodedcommand|-windowstyle hidden)")
| eval technique="T1059.001"
| table _time, Computer, User, CommandLine, technique
```

## Testing Methodology

### Unit Testing
- Test individual rule components
- Verify expected matches and exclusions
- Validate metadata accuracy

### Integration Testing
- Test in realistic environment
- Use production-like data volumes
- Assess performance impact

### Red Team Validation
- Execute actual attack techniques
- Verify detection triggers correctly
- Measure detection timing

## Performance Considerations

### Optimization Techniques
- Use indexed fields when possible
- Avoid expensive regex operations
- Implement time-based filtering
- Use efficient data types

### Monitoring Metrics
- Rule execution time
- Resource consumption
- False positive rates
- Detection coverage gaps

## Documentation Requirements

Every detection rule must include:
- Clear business justification
- Technical implementation details
- Testing results and methodology
- Maintenance procedures
- Escalation procedures for alerts
