---
name: MCP Server Request
about: Request approval to add a new MCP server to the organization registry
title: "[MCP] "
labels: mcp-server, infrastructure, needs-review
assignees: ''
---

## MCP Server Information

**Server Name:**
<!-- e.g., playwright, database-reader, custom-deploy -->

**Version:**
<!-- e.g., 1.0.0 -->

**Source/Package:**
<!-- e.g., npx @playwright/mcp@latest, custom Docker image -->

---

## Purpose & Justification

**What problem does this MCP server solve?**
<!-- Describe the business or technical need -->

**Why can't existing MCP servers handle this?**
<!-- Explain why current capabilities are insufficient -->

**Who will use this MCP server?**
<!-- e.g., AI agents for testing, human developers for debugging -->

---

## Capabilities Requested

**List all tools/capabilities this MCP server provides:**
<!-- Bullet list of specific capabilities -->
-
-
-

**Example usage scenarios:**
<!-- Provide 2-3 concrete examples of how this will be used -->
1.
2.
3.

---

## Security Review

### Network Access Requirements
<!-- Does this server need network access? If yes, to what destinations? -->
- [ ] No network access required
- [ ] Localhost only
- [ ] Specific external domains: [list here]
- [ ] Unrestricted internet access (⚠️ requires strong justification)

### File System Access Requirements
<!-- Does this server need file system access? If yes, to what paths? -->
- [ ] No file system access
- [ ] Read-only access to: [specify paths]
- [ ] Write access to: [specify paths]

### Credentials/Secrets Required
<!-- Will this server need access to any credentials or secrets? -->
- [ ] No credentials required
- [ ] Requires credentials: [describe what and how stored]

### Data Handling
<!-- What data will this server process? -->
- [ ] No sensitive data
- [ ] User data: [describe]
- [ ] System data: [describe]
- [ ] PII: [describe]

**Data retention policy:**
<!-- How long is data stored? Where? -->

---

## Resource Requirements

**Expected resource usage:**
- **Memory:** [e.g., <100MB, <500MB]
- **CPU:** [e.g., <5%, <20%]
- **Disk:** [e.g., none, <1GB]

**Concurrency limits:**
<!-- Max concurrent requests/connections -->

---

## Testing Plan

**Local testing completed:**
- [ ] Tested server locally using `.claude/settings.local.json`
- [ ] Verified all capabilities work as expected
- [ ] Tested error handling and edge cases
- [ ] Measured resource usage
- [ ] Reviewed audit logs

**Testing notes location:**
<!-- Link to testing documentation or attach as comment -->

**Issues found during testing:**
<!-- List any issues and how they were resolved -->

---

## Sandbox/Isolation Strategy

**How will this server be isolated?**
- [ ] Runs in Docker container
- [ ] Runs in separate process
- [ ] Runs in-process (⚠️ requires justification)

**Resource limits enforced:**
- [ ] Memory limits: [specify]
- [ ] CPU limits: [specify]
- [ ] Network policies: [specify]

**Failure modes:**
<!-- What happens if the server crashes or misbehaves? -->

---

## Audit & Logging

**Logging strategy:**
<!-- What events are logged? Where? -->

**Audit trail:**
<!-- How can usage be traced back to specific agents/users? -->

**Monitoring:**
<!-- How will server health and usage be monitored? -->

---

## Deployment

**Deployment method:**
- [ ] npm package (via npx)
- [ ] Docker image (publish to ghcr.io)
- [ ] System binary
- [ ] Custom deployment: [describe]

**Docker image (if applicable):**
<!-- Provide Dockerfile or link to image -->

**Configuration required:**
<!-- Environment variables, config files, etc. -->

---

## Documentation

**Links to documentation:**
<!-- Official docs, README, API reference -->
-

**Custom documentation needed:**
<!-- What additional docs should be created for internal use? -->

---

## Risk Assessment

**Overall risk level:** [Low / Medium / High]

**Identified risks:**
1.
2.
3.

**Mitigation strategies:**
1.
2.
3.

---

## Approval Checklist

**Reviewed by:**
- [ ] Requesting developer (local testing complete)
- [ ] team.human.seniors (technical review)
- [ ] Security team (security review)
- [ ] team.org.owners (final approval)

**Approval criteria:**
- [ ] Business justification is clear
- [ ] Security concerns addressed
- [ ] Testing is thorough
- [ ] Documentation is adequate
- [ ] Resource usage is acceptable
- [ ] Aligns with operating model governance

---

## Additional Notes

<!-- Any other relevant information -->

---

**See also:** [MCP Server Workflow Guide](../../docs/tooling/mcp-server-workflow.md)
