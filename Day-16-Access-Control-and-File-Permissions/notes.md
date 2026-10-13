\# Day 16 — Access Control and Windows File Permissions



\## 1. Objectives



\- Understand Role-Based Access Control (RBAC).

\- Understand Attribute-Based Access Control (ABAC).

\- Understand the principle of least privilege.

\- Explore Windows local users and groups.

\- Inspect folder and file permissions.

\- Test the access available to a standard user account.

\- Document the results of a Windows permissions investigation.



\## 2. Security+ Study Notes



\### Role-Based Access Control (RBAC)



RBAC assigns permissions according to a user's role in an organization.



Examples:

\- An accountant receives access needed for accounting tasks.

\- An HR officer receives access needed for HR tasks.

\- An IT administrator receives administrative permissions.



\*\*Key point:\*\* RBAC means Role-Based Access Control.



\### Attribute-Based Access Control (ABAC)



ABAC makes access decisions using attributes associated with the user, resource, requested action, or environment.



Examples of attributes include:

\- User identity or department.

\- Device being used.

\- Resource being requested.

\- Time of day.



\*\*Key point:\*\* ABAC can evaluate multiple attributes when making an access decision.



\### Principle of Least Privilege



Least privilege means giving a user or account only the permissions necessary to perform its required tasks.



Benefits:

\- Reduces unnecessary access.

\- Limits accidental or unauthorized changes.

\- Helps reduce the impact of compromised accounts.

\- Supports a stronger security posture.



\### Windows Users, Groups, and Permissions



Windows local accounts represent individual users. Groups help administrators assign permissions to multiple users through group membership.



Windows file and folder permissions control the actions an account or group can perform.



Common permissions include:

\- \*\*Read:\*\* View file contents.

\- \*\*Read \& execute:\*\* Read files and execute applicable programs.

\- \*\*List folder contents:\*\* View items in a folder.

\- \*\*Write:\*\* Create or change data where permitted.

\- \*\*Modify:\*\* Read, write, and make changes, including deletion where allowed.

\- \*\*Full control:\*\* Includes broader permission-management capabilities.



The effective access a user receives depends on the applicable permissions, group membership, inheritance, and other access-control rules.



\## 3. Lab Environment



\- Virtual machine: Windows Server 2025 Standard Evaluation.

\- Administrative account: Administrator.

\- Standard test account: LabUser15.

\- Test folder: `C:\\SecurityLab`

\- Test file: `C:\\SecurityLab\\Access-Test.txt`

\- Tool used: Computer Management and File Explorer Properties → Security.



\## 4. Lab Procedure



\### Task 1 — Inspect local user accounts



Opened Computer Management and navigated to:



`Computer Management → System Tools → Local Users and Groups → Users`



Inspected the available local accounts and the properties of the Administrator and LabUser15 accounts.



\### Task 2 — Inspect local groups



Navigated to:



`Computer Management → System Tools → Local Users and Groups → Groups`



Inspected the Administrators and Users groups and viewed their membership information.



\### Task 3 — Create a test file



Created the folder:



`C:\\SecurityLab`



Created a text file inside it:



`C:\\SecurityLab\\Access-Test.txt`



Added the following test text:



`Day 16 Security+ lab: testing Windows file permissions.`



\### Task 4 — Inspect folder permissions



Opened the Security tab in the properties of `C:\\SecurityLab`.



Reviewed the entries for groups and security principals, including SYSTEM, Administrators, and Users.



Observed that the Users group had Allow permissions for:

\- Read \& execute.

\- List folder contents.

\- Read.



Full control, Modify, and Write were not visibly allowed for the Users group in the displayed permissions.



\### Task 5 — Inspect file permissions



Opened the Security tab in the properties of `Access-Test.txt`.



Observed that the Users group had Allow permissions for Read and Read \& execute. Write, Modify, and Full control were not visibly allowed for that group.



The Administrators and SYSTEM entries displayed broader Allow permissions, including Full control, Modify, Read \& execute, Read, and Write.



\### Task 6 — Test access as LabUser15



Signed in to Windows using the standard account LabUser15 and navigated to `C:\\SecurityLab`.



Opened `Access-Test.txt` in Notepad. The file contents were accessible for reading.



Typed additional text into Notepad and attempted to save the changes.



Windows displayed a permission error for `C:\\SecurityLab\\Access-Test.txt`, stating that permission was not available and advising the user to contact the owner or an administrator.



This demonstrated that being able to view content in an editing application does not guarantee permission to save changes to the existing file.



\### Task 7 — Return to Administrator



Signed back in as Administrator and reviewed the Security tab for `C:\\SecurityLab` again.



No permission settings were intentionally changed during the investigation.



\## 5. Results and Findings



1\. Windows provides local user accounts and groups for managing access.

2\. The Administrators group displayed broader permissions than the Users group on the test file.

3\. The Users group had limited visible permissions on the SecurityLab folder and test file.

4\. LabUser15 could open and read the test file.

5\. When attempting to save a change, Windows displayed a permission error.

6\. The lab illustrated the difference between viewing a file and being able to modify it.

7\. Restricting unnecessary write and modification permissions supports least privilege.



\*\*Important observation:\*\* The save attempt was blocked by a Windows permission error. This is the observed result of the test; it should not be interpreted as proof that every file on the system has the same permissions.



\## 6. Troubleshooting Notes



\- When File Explorer displayed search results instead of opening the folder, used the address bar to navigate directly to `C:\\SecurityLab`.

\- When Notepad displayed Save As, checked the file path and avoided intentionally creating a second test file.

\- When the save attempt displayed a permission error, captured the result as evidence.

\- No access permissions were intentionally changed during this lab.



\## 7. Screenshot Evidence



Save the useful screenshots in the Day 16 `screenshots` folder. Use the following names for the corresponding evidence:



| Screenshot filename | Evidence to show |

|---|---|

| `01-Local-User-Accounts.png` | Local Users and Groups → Users list. |

| `02-Administrator-Account-Properties.png` | Administrator account properties. |

| `03-Local-Groups-Overview.png` | Local Users and Groups → Groups list. |

| `04-Administrators-Group-Membership.png` | Administrators group membership. |

| `05-Users-Group-Membership.png` | Users group membership. |

| `06-LabUser15-Account-Properties.png` | LabUser15 account properties. |

| `07-LabUser15-Group-Membership.png` | LabUser15 Member Of tab showing Users membership. |

| `12-SecurityLab-Test-File-Created.png` | `Access-Test.txt` inside `C:\\SecurityLab`. |

| `13-Access-Test-File-Contents.png` | Test sentence visible in Notepad. |

| `14-Access-Test-File-Permissions.png` | File Security tab with Users selected. |

| `15-Access-Test-Administrator-Permissions.png` | File Security tab with Administrators selected. |

| `16-Access-Test-SYSTEM-Permissions.png` | File Security tab with SYSTEM selected. |

| `17-Test-User-File-Read-Access.png` | Test file open and readable as LabUser15. |

| `18-Test-User-File-Save-Permission.png` | Windows permission error during the save attempt. |

| `19-SecurityLab-Folder-Permissions.png` | Security tab for `C:\\SecurityLab`. |

| `20-SecurityLab-Folder-Users-Permissions.png` | Folder Security tab with Users selected. |



\*\*Evidence note:\*\* Use the filenames above for screenshots that were actually captured and saved. Screenshots 8–11 and 12–16 should be checked against your existing folder before finalizing the list. Do not claim that a screenshot exists if it was not saved. The screenshot numbering can be adjusted to match the evidence you actually retained.



\## 8. What I Learned



\- RBAC assigns permissions according to roles.

\- ABAC evaluates attributes when deciding whether access should be granted.

\- Least privilege reduces unnecessary access.

\- Windows uses users, groups, and access permissions to control resources.

\- Folder permissions and file permissions are related but distinct.

\- Read access does not automatically guarantee write or modification access.

\- Testing permissions using a standard account helps verify the practical effect of access-control settings.

\- Screenshots and recorded results make a security investigation easier to explain and reproduce.



\## 9. Lab Conclusion



The Day 16 lab explored access-control concepts and Windows local users, groups, and file permissions. A test file was created in `C:\\SecurityLab`, and its permissions were inspected for Users, Administrators, and SYSTEM.



The standard account LabUser15 could read the test file, but Windows displayed a permission error when saving the attempted modification. This provided practical evidence of how Windows permissions can restrict changes to a resource.



The exercise reinforced RBAC, ABAC, least privilege, and the importance of validating access permissions rather than assuming that a user can perform every action on a file.



\## 10. Safety and Scope



This investigation was performed in my own Windows Server lab. No production systems were targeted, and no permission settings were intentionally changed.



