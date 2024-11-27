---
title: About Cryptography and Hashing
date: 2024-11-22 10H:36:00 -0300
categories: [Distributed Systems, Algorithms]
tags: [cryptography, computing-fundamentals, hashing-algorithms, crypthographic-algorithms]
author: 0
description:
image:
  path: https://upload.wikimedia.org/wikipedia/commons/thumb/0/00/Asymmetric_encryption.xcf/640px-Asymmetric_encryption.xcf.png
  alt: Picture
---
# About Cryptographic and Hashing Algorithms

*Frequent uses of cryptographic algorithms.*
* Sensitive data storage
* Data transmission with cryptographic keys
* Checksums, reduction algorithms 
* Fingerprints on certificates   
* In the implementation of blockchain systems


*Some Algorithms*
* SHA-1, hash {obsolet}
* MD5, hash {obsolet}
* SHA256, hash
* SHA512, hash
* TIB3, hash
* AES, symmetrical
* Blowfish, symmetrical
* DES, symmetrical
* RSA, asymmetric  


**Method for storing passwords using encryption algorithms**
* Simple: An encryption algorithm is chosen. The user records the password, and instead of storing it, the system saves the transformation of the encryption algorithm into the password. Every time the user wants to access, the transformation will be performed again to see if it matches the one that the system considers valid. If an encryption algorithm becomes obsolete, such as SHA-1 or MD5, it will be easy for an attacker    
* SALT: Password storage technique. Here the difficulty for the attacker to reveal the password increases, since what is saved is not only the result of the transformation of the password, but other user data is used. An example of common use is to use the user identifier, then before performing the transformation, some type of operation is performed between the password and the user data.  
