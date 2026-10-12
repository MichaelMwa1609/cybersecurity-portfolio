# Day 15: Identity and Access Management (IAM)

## 1. Security+ Topics Covered
- Identity and Access Management (IAM)
- User account management
- Authentication and password requirements
- Authorization and group membership
- Principle of least privilege
- Standard users versus administrators

## 2. What I Learned
I learned that Identity and Access Management (IAM) controls who can access a system and what actions they are allowed to perform.

- **Authentication:** Verifies a user's identity.
- **Authorization:** Determines what resources and actions a user can access.
- **Least privilege:** Users should receive only the permissions needed for their responsibilities.
- **Group membership:** Determines which permissions a user may receive.
- **Password requirements:** Help enforce account security.

## 3. What I Did in the Lab
I used Windows Server 2025 to create and verify a local test user account.

1. Created the account `LabUser15`.
2. Set the full name to `Day 15 Test User`.
3. Added a description for the Security+ IAM lab.
4. Configured the account to require a password change at the next logon.
5. Signed in as the test user.
6. Ran `whoami` to verify the logged-in identity.
7. Ran `whoami /groups` to inspect group memberships.
8. Used `Get-LocalUser` to check the account status and password requirements.
9. Used `Get-LocalGroupMember -Group "Administrators"` to inspect the local Administrators group.

## 4. Results
- The `LabUser15` account was enabled.
- A password was required.
- The account was not listed in the local Administrators group.
- The built-in Administrator account was listed in the Administrators group.

## 5. Security Lessons
- Apply least privilege when assigning user permissions.
- Avoid giving standard users unnecessary administrator access.
- Review account settings and group memberships.
- Verify security configurations instead of assuming they are correct.
- Keep screenshots as evidence of completed lab work.

## 6. Evidence
Screenshot: `14-user-account-and-admin-group-verification.png`

## 7. Conclusion
This lab provided practical experience with Windows local user accounts, password requirements, PowerShell commands, and group membership verification. These skills support my understanding of Security+ Identity and Access Management concepts.





