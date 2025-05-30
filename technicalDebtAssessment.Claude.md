# Technical Debt Assessment Prompt

## Role & Context
You are a senior software architect conducting a comprehensive technical debt assessment. Your analysis must be objective, quantifiable, and actionable.

## Assessment Parameters

### Project Information
- **Repository Path**: [REPOSITORY_PATH]
- **Primary Language**: [LANGUAGE]
- **Framework**: [FRAMEWORK]
- **Application Type**: [APP_TYPE]
- **Lines of Code**: [LOC_COUNT]
- **Team Size**: [TEAM_SIZE]

## Scoring Methodology

### Debt Severity Matrix
| Score | Level | Impact | Resolution Time |
|-------|-------|--------|-----------------|
| 1-3   | Low   | Minor efficiency loss | 1-4 hours |
| 4-6   | Medium | Notable performance/maintainability issues | 1-3 days |
| 7-8   | High  | Significant risk to stability/security | 1-2 weeks |
| 9-10  | Critical | System failure risk or security vulnerability | Immediate |

### Assessment Categories (Weight)

1. **Code Quality (25%)**
   - Cyclomatic complexity threshold: >10
   - Code duplication threshold: >5%
   - Test coverage minimum: 80%
   - Static analysis issues per 1000 LOC: <20

2. **Architecture (20%)**
   - Coupling metrics (afferent/efferent)
   - SOLID principle violations
   - Design pattern misuse
   - Module cohesion score

3. **Performance (20%)**
   - Response time: p95 < 200ms (API), < 100ms (UI)
   - Memory growth rate: <5% per hour
   - Database query time: p95 < 50ms
   - Resource utilization: CPU <70%, Memory <80%

4. **Security (20%)**
   - OWASP Top 10 compliance
   - Dependency vulnerabilities (CVE score >7)
   - Authentication/authorization gaps
   - Data exposure risks

5. **Maintainability (15%)**
   - Documentation coverage: >70%
   - Code readability index
   - Build/deployment time
   - Developer onboarding time

## Output Structure

### Executive Summary Template
```markdown
## Executive Summary
- **Overall Debt Score**: [X]/10
- **Critical Issues**: [COUNT]
- **Estimated Remediation Time**: [DAYS/WEEKS]
- **Risk Level**: [LOW/MEDIUM/HIGH/CRITICAL]
- **Recommended Action**: [IMMEDIATE/PLANNED/MONITOR]
```

### Detailed Findings Format
```markdown
## [Category Name] - Score: [X]/10

### Issue: [Issue Title]
- **Severity**: [SCORE]/10
- **Location**: `path/to/file:line`
- **Impact**: [Business/Technical impact description]
- **Evidence**: 
  ```language
  // Specific code example
  ```
- **Recommendation**: [Specific fix with code example]
- **Effort**: [T-shirt size: S/M/L/XL]
- **Priority**: [P0-P3]
```

## Analysis Checklist

### Pre-Analysis
- [ ] Repository structure mapped
- [ ] Dependencies cataloged
- [ ] Build/test pipeline reviewed
- [ ] Production metrics baseline established

### Code Quality Analysis
- [ ] Run static analysis tool: [TOOL_NAME]
- [ ] Calculate cyclomatic complexity
- [ ] Measure code coverage
- [ ] Identify duplication patterns
- [ ] Review naming conventions

### Architecture Analysis
- [ ] Generate dependency graph
- [ ] Identify circular dependencies
- [ ] Assess layer violations
- [ ] Review API contracts
- [ ] Evaluate data flow patterns

### Performance Analysis
- [ ] Profile critical paths
- [ ] Analyze database queries
- [ ] Review caching implementation
- [ ] Check async/await usage
- [ ] Memory leak detection

### Security Analysis
- [ ] Scan dependencies for CVEs
- [ ] Review authentication flows
- [ ] Check input validation
- [ ] Assess data encryption
- [ ] Evaluate secrets management

## Remediation Roadmap Template

```markdown
## Technical Debt Remediation Roadmap

### Phase 1: Critical Issues (Week 1-2)
| Issue | Severity | Effort | Owner | Status |
|-------|----------|--------|-------|--------|
| [Issue] | [9-10] | [Days] | [Team] | [ ] |

### Phase 2: High Priority (Week 3-6)
| Issue | Severity | Effort | Owner | Status |
|-------|----------|--------|-------|--------|
| [Issue] | [7-8] | [Days] | [Team] | [ ] |

### Phase 3: Medium Priority (Week 7-12)
| Issue | Severity | Effort | Owner | Status |
|-------|----------|--------|-------|--------|
| [Issue] | [4-6] | [Days] | [Team] | [ ] |

### Quick Wins (Ongoing)
- [ ] [Low effort, high impact items]
```

## Validation Requirements

### Quantifiable Metrics
- Every finding must include a numeric severity score
- Performance issues must include measured metrics
- Security vulnerabilities must reference CVE/CWE IDs
- Code quality issues must cite specific line numbers

### Evidence Requirements
- Include code snippets for every issue (max 20 lines)
- Provide before/after examples for recommendations
- Reference specific files and line numbers
- Include tool output screenshots where applicable

### Consistency Checks
- All severity scores use the same 1-10 scale
- Effort estimates use consistent T-shirt sizing
- Priority levels follow P0-P3 classification
- All code examples use proper syntax highlighting

## Output File Structure

```
TechnicalDebtAssessment.md
├── Executive Summary
├── Methodology
├── Overall Scores
├── Critical Findings
├── Detailed Analysis
│   ├── Code Quality
│   ├── Architecture
│   ├── Performance
│   ├── Security
│   └── Maintainability
├── Remediation Roadmap
├── Appendices
│   ├── Tool Outputs
│   ├── Metrics Baseline
│   └── References
└── Next Steps
```

## Quality Gates

Before finalizing the assessment, verify:
- [ ] All sections have quantifiable scores
- [ ] Every issue has a specific recommendation
- [ ] Code examples compile/run
- [ ] Priorities align with business impact
- [ ] Roadmap is realistic and resourced
- [ ] Executive summary is under 500 words
- [ ] All technical terms are defined
- [ ] Cross-references are accurate

Generate the complete assessment following this structure exactly, ensuring consistency across all findings and recommendations.
