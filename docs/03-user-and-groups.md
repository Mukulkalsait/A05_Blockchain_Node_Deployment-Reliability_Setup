# User and Group Management

## Objective
Apply least-privilege principles by avoiding root usage for daily operations and services.

## User Strategy
- Created a dedicated non-root operational user
- Granted sudo access for administrative tasks
- Avoided shared or generic user accounts

## Group Management
- Used default sudo group for controlled privilege escalation
- No unnecessary group memberships added

## Security Rationale
- Reduces risk of accidental system-wide changes
- Improves auditability of actions
- Aligns with production server best practices

## Validation
- Confirmed sudo access for administrative commands
- Verified SSH access using non-root user

