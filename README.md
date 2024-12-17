# **Lab 1: Basic Cryptography - AES, RSA, and Kyber**

---

## **1. Introduction**

This lab explores three cryptographic algorithms:  
1. **AES** (Advanced Encryption Standard)  
2. **RSA** (Rivest-Shamir-Adleman)  
3. **CRYSTALS-Kyber** (Post-Quantum Cryptography)  

The lab is divided into three modules:  
1. **Performance Analysis** of AES, RSA, and Kyber.  
2. Experimentation with AES encryption modes (**ECB** and **CBC**).  
3. **Secure Communication** with a server to retrieve a secret message using RSA or Kyber.  

---

## **2. Lab Modules**

### **Module 1: Performance of Ciphers**

This module evaluates the performance of three cryptographic functions:  
- **AES_encrypt** (AES-128)  
- **RSA_public_encrypt** (RSA)  
- **PQCLEAN_KYBER512_CLEAN_crypto_kem_enc** (Kyber512)

#### **Findings**:
- **AES**: Most encryption times are below **100,000 CPU cycles**, with many samples under **50,000 cycles**.  
- **RSA**: Significantly slower, with encryption times frequently exceeding **10,000,000 CPU cycles**.  
- **Kyber**: Faster than RSA but around **10 times slower** than AES.

#### **Performance Comparison**:
| **Algorithm**  | **Speed**                 | **Use Case**                                      |
|----------------|---------------------------|--------------------------------------------------|
| **AES-128**   | Fast (High Performance)   | High-speed data encryption (e.g., TLS, cloud storage). |
| **RSA**       | Slow (10-100x slower)     | Secure key exchange and digital signatures.      |
| **Kyber512**  | Faster than RSA (Post-Quantum) | Secure key exchange with quantum resistance.     |

**Why Use Kyber Over RSA?**  
- Kyber provides enhanced security against **quantum computing threats**.  
- It offers **better performance** compared to RSA in terms of encryption and decryption speed.  

---

### **Module 2: AES Encryption Modes**

This module compares two AES encryption modes:  
1. **ECB** (Electronic Code Book)  
2. **CBC** (Cipher Block Chaining)  

#### **Findings**:
1. **ECB Mode**:  
   - **Visible Patterns**: The structure of the original image is still visible.  
   - **Security Implications**: Not secure for encrypting structured data with repeating patterns.  

2. **CBC Mode**:  
   - **No Visible Patterns**: The encrypted image appears random, hiding the original structure.  
   - **Security Advantage**: More secure than ECB mode.  

#### **Conclusion**:  
- CBC mode is preferred for image encryption due to its ability to hide patterns.  

---

### **Module 3: Secure Communication**

This module focuses on establishing secure communication between the client and server to retrieve a **16-byte secret message**. Two approaches are provided:  
1. **Option 1: RSA**  
2. **Option 2: Kyber (Post-Quantum Secure)**  


---

## **4. Key Findings**

1. **Performance**:  
   - **AES** is the fastest encryption algorithm.  
   - **Kyber512** is **10x slower** than AES but significantly faster than RSA.  
     - Kyber is a suitable **post-quantum alternative** to RSA for secure key exchange.  

2. **Security**:  
   - **CBC Mode** hides patterns better than **ECB Mode**, ensuring better security for encrypted images.  

3. **Post-Quantum Readiness**:  
   - Kyber512 provides strong protection against potential **quantum computing threats**, making it a future-proof solution.

---

## **5. Challenges Faced**

1. **Timing Analysis**:  
   - Collecting and processing **1,000,000 timing samples** required optimization and careful plotting.  

2. **Image Encryption**:  
   - Understanding the behavior of **ECB** and **CBC** modes when encrypting structured data (e.g., images).  

3. **Secure Communication**:  
   - Proper implementation of the **client-server protocol** using RSA and Kyber encryption to retrieve the secret message.

---

## **6. Lessons Learned**

1. **Cryptographic Algorithms**:  
   - Practical implementation of AES, RSA, and Kyber highlighted their performance and use cases.  

2. **Performance vs. Security**:  
   - Gained insight into balancing **encryption speed** (AES) and **quantum resistance** (Kyber).  

3. **Encryption Modes**:  
   - **ECB** is insecure for structured data, while **CBC** hides patterns effectively and enhances security.  

4. **Secure Communication**:  
   - Learned to implement **client-server communication** protocols using RSA and Kyber for key exchange and AES for message encryption.

---

## **7. References**

1. Stinson, D. R., & Vanstone, S. A. (2005). *Cryptography: Theory and Practice (3rd ed.)*. CRC Press.  
2. Katz, J., & Lindell, Y. (2014). *Introduction to Modern Cryptography: Principles and Protocols (2nd ed.)*. Chapman and Hall/CRC.  
3. Daemen, J., & Rijmen, V. (2002). *AES: The Advanced Encryption Standard*. In *The Block Cipher Companion* (pp. 77-105). Wiley.  
4. Hoffstein, J., Pipher, J., & Silverman, J. (2017). *An Introduction to Post-Quantum Cryptography*. Advances in Cryptology – ASIACRYPT 2017. Springer. [https://doi.org/10.1007/978-3-319-70600-2_9](https://doi.org/10.1007/978-3-319-70600-2_9).  
5. Koblitz, N. (1987). *Elliptic Curve Cryptosystems*. Mathematics of Computation, 48(177), 203-209. [https://doi.org/10.1090/S0025-5718-1987-08722-3](https://doi.org/10.1090/S0025-5718-1987-08722-3).  

---

## **8. Author**

**Germain Mucyo**  
**Email**: [mucyo.g@northeastern.edu](mailto:mucyo.g@northeastern.edu)

