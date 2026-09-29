# entra-guest-manager-remediation
# Entra Guest Manager Remediation

## Purpose
Populate the Manager attribute for guest users using their Sponsor relationship.

## Prerequisites
- Global Reader (for reporting)
- User Administrator (for updates)
- Azure CLI authenticated
- Microsoft Graph permissions

## Process

1. Export guest users.
2. Check existing managers.
3. Identify sponsor relationships.
4. Backup current assignments.
5. Update manager attribute.
6. Validate results.
7. Generate final report.

## Validation

Verify remaining guests without managers:

```powershell
($Results | Where-Object {$_.HasManager -eq "No"}).Count
