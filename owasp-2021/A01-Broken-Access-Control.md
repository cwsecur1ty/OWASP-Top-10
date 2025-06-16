# A01 - Broken Access Control
Users can access stuff they shouldn't. Think admin panels, other user's data, or restricted files.

### Common Attacks
- Direct URL access to admin pages
- Changing user IDs in requests
- Accessing APIs without proper auth

### Log Indicators
- 403 errors followed by 200s on same resource
- Unusual file access patterns
- Privilege escalation attempts

### MITRE Mapping
- T1078 (Valid Accounts)
- T1134 (Access Token Manipulation)

### Detection Query (Elastic)
- `status_code:200 AND url:*/admin/* AND NOT user_role:admin`
  
### Quick Fixes
- Implement proper RBAC
- Default deny access
- Log all access attempts