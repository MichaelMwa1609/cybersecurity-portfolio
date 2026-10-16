\# Day 18: PKI, Certificates, and Digital Signatures



\## 1. Objective



The objective of this lab was to inspect a website's digital certificate and understand how Public Key Infrastructure (PKI), certificate authorities, digital signatures, validity periods, and public keys support secure communications.



\## 2. Lab Environment



\- Operating system: Windows Server lab VM

\- User account: LabUser15 (Day 15 test account)

\- Browser: Microsoft Edge

\- Website inspected: https://www.google.com

\- Tool used: Browser Certificate Viewer

\- Repository: Security Plus

\- Evidence folder: `screenshots/`



\## 3. Concepts Learned



\### Public Key Infrastructure (PKI)



PKI is the framework used to manage digital certificates and public-key cryptography. It helps systems establish trust in the relationship between an identity and a public key.



\### Certificate Authority (CA)



A Certificate Authority issues and digitally signs certificates to help establish trust in the information they contain.



\### Digital Certificates



A digital certificate associates an identity with a public key and contains information such as the issuer, validity period, and cryptographic algorithms.



\### Digital Signatures



Digital signatures help verify data integrity and the association between a signature and the corresponding public key. They do not, by themselves, encrypt the signed data.



\### Public and Private Keys



A public key can be shared. Its corresponding private key must be protected. Public-key cryptography supports activities such as digital signatures and secure key establishment.



\## 4. Lab Methodology



1\. Signed in to the Windows Server lab VM using the Day 15 test account.

2\. Opened Microsoft Edge.

3\. Navigated to `https://www.google.com`.

4\. Opened the website's Certificate Viewer.

5\. Examined the General tab to identify the website, issuer, validity period, and SHA-256 fingerprints.

6\. Opened the Details tab and inspected the certificate hierarchy.

7\. Examined the certificate signature algorithm.

8\. Inspected the issuer information.

9\. Examined the certificate validity fields.

10\. Inspected the subject public key and public-key algorithm.

11\. Examined the certificate key-usage extension.

12\. Captured screenshots as evidence of the inspection.



\## 5. Findings



\### Website Identity



\- Certificate subject common name: `www.google.com`

\- Issuer common name: `WR2`

\- Issuer organization: `Google Trust Services`

\- Issuer country: `US`



\### Certificate Signature Algorithm



The Certificate Viewer displayed:



`PKCS #1 SHA-256 With RSA Encryption`



This identifies the signature algorithm shown for the certificate. SHA-256 is the hash function, and RSA is the public-key cryptographic algorithm used in the signature scheme.



\### Certificate Validity



The General tab displayed the certificate's issue and expiry dates. The Details tab contained the `Not Before` and `Not After` fields.



The validity period helps determine when a certificate is intended to be accepted, subject to other certificate-validation checks.



\### Public-Key Information



The public-key field was inspected in the Certificate Viewer.



The Subject Public Key Algorithm field displayed:



`Elliptic Curve Public Key`



This indicates that the certificate's subject public key uses elliptic-curve cryptography.



\### Certificate Key Usage



The Certificate Key Usage field displayed:



`Critical Signing`



The critical designation means that software validating the certificate must understand and process the extension or reject the certificate. The signing usage indicates a signing-related purpose.



\### Certificate Hierarchy



The Certificate Viewer showed a hierarchy containing:



\- `GTS Root R1`

\- `WR2`

\- `www.google.com`



This demonstrates how a website certificate can be linked to an issuing certificate and a root certificate in a trust chain.



\## 6. Security Significance



\- Certificate identity information helps a browser validate which website a certificate represents.

\- Certificate authorities help establish trust in certificates.

\- Certificate validity dates help identify certificates that are outside their intended validity period.

\- Digital signatures help detect changes to signed data and verify the signature against the corresponding public key.

\- Certificate revocation checking is important because a certificate can be revoked before its expiry.

\- Public keys may be distributed, while private keys must remain protected.

\- Certificate chains allow trust to be established through issuing and root certificates.



\## 7. Evidence and Screenshots



The following screenshots were saved in the `screenshots/` folder:



1\. `day18-01-certificate-general.png`

2\. `day18-02-certificate-details.png`

3\. `day18-03-signature-algorithm.png`

4\. `day18-04-certificate-issuer.png`

5\. `day18-05-certificate-validity.png`

6\. `day18-06-certificate-expiry.png`

7\. `day18-07-certificate-public-key.png`

8\. `day18-08-public-key-algorithm.png`

9\. `day18-09-certificate-key-usage.png`



\## 8. Verification



The certificate information was inspected through the browser's Certificate Viewer. The issuer, signature algorithm, public-key information, and key-usage extension were visible in the certificate details.



The certificate was inspected without changing its configuration or exporting private-key material.



\## 9. Lessons Learned



\- PKI provides a framework for managing certificates and public-key trust.

\- Certificate authorities issue and digitally sign certificates.

\- Certificate fields provide information about identity, issuer, validity, and cryptographic algorithms.

\- Digital signatures support integrity and verification.

\- Public and private keys have different roles and must be handled appropriately.

\- Certificate chains help browsers establish trust in website certificates.

\- Certificate validity and revocation are separate considerations.



\## 10. Conclusion



This lab provided practical experience inspecting a website certificate and identifying its issuer, signature algorithm, public-key algorithm, validity information, certificate hierarchy, and key-usage extension.



The exercise reinforced the role of PKI and digital certificates in establishing trust and supporting secure communications.



\## 11. Safety and Scope



The activity was limited to viewing publicly presented certificate information for a website. No certificate settings were changed, and no private keys were exported or collected.



