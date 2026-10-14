\# Day 17: Encryption and Hashing



\## 1. Objective

The objective of this lab was to understand SHA-256 hashing and demonstrate how cryptographic hashes can be used to verify file integrity and detect changes.



\## 2. Security+ Topics Studied



\### Symmetric Encryption

Symmetric encryption uses the same secret key to encrypt and decrypt data. AES is a common example. It is efficient for encrypting large amounts of data.



\### Asymmetric Encryption

Asymmetric encryption uses a public and private key pair. RSA and ECC are examples of asymmetric cryptography.



\### Hashing

Hashing converts input data into a fixed-length digest. It can help verify data integrity by detecting unexpected changes.



\### SHA-256

SHA-256 is a cryptographic hash function that produces a 256-bit digest. Hashing is not encryption and is not designed to be reversed to recover the original file.



\### Digital Signatures

Digital signatures help verify message integrity and authenticity using asymmetric cryptography.



\### Key Management

Cryptographic keys must be protected against unauthorized access. Good key management includes access controls, secure backups, rotation, and revocation when necessary.



\### Data at Rest and Data in Transit

\- Data at rest is stored on a device or storage medium.

\- Data in transit is moving between systems over a communication channel.

\- Encryption helps protect confidentiality in both situations.



\## 3. Lab Environment

\- Operating system: Ubuntu Linux

\- Tool: SHA-256 utility (`sha256sum`)

\- Test file: `day17\_test.txt`

\- Checksum file: `day17\_hash.txt`



\## 4. Commands Used



Display the current user:

`whoami`



Display the current working directory:

`pwd`



Create the test file:

`echo "Security Plus Day 17 - Hashing and File Integrity" > day17\_test.txt`



Display the file:

`cat day17\_test.txt`



Calculate its SHA-256 hash:

`sha256sum day17\_test.txt`



Save the original hash:

`sha256sum day17\_test.txt > day17\_hash.txt`



Verify the saved hash:

`sha256sum -c day17\_hash.txt`



Modify the test file:

`echo "This is an additional line." >> day17\_test.txt`



Check the file again:

`sha256sum -c day17\_hash.txt`



Compare the modified hash with the original:

`sha256sum day17\_test.txt`

`cat day17\_hash.txt`



Check the SHA-256 utility version:

`sha256sum --version`



\## 5. Lab Results

1\. Created a test file in Ubuntu.

2\. Calculated its SHA-256 hash.

3\. Saved the original hash in a separate file.

4\. Verified the unchanged file successfully.

5\. Added another line to the test file.

6\. Repeated verification and observed a failed integrity check.

7\. Compared the modified file's hash with the saved original hash and observed that the values differed.



\## 6. Security Significance

SHA-256 checksums can help detect accidental or unauthorized file changes when compared against a trusted checksum. A checksum alone does not prove who created a file or guarantee that the file is safe. The checksum itself must come from a trustworthy source.



\## 7. What I Learned

\- The difference between symmetric and asymmetric encryption.

\- How SHA-256 produces a digest from file contents.

\- How to calculate and save a checksum in Ubuntu.

\- How to verify file integrity with `sha256sum -c`.

\- Why modifying a file causes its hash to normally change.

\- The purpose of digital signatures and secure key management.

\- The difference between data at rest and data in transit.



\## 8. Evidence

Screenshots are saved in the `screenshots` folder.



\## 9. Conclusion

This lab demonstrated how SHA-256 hashing can be used to check file integrity. The original file passed verification, while the modified file failed against the original saved checksum. This practical exercise reinforced the importance of integrity checking in cybersecurity.

