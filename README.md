# HelLibpt2

This project explores Homomorphic Encryption (HE), a groundbreaking form of encryption that enables computation on encrypted data, producing an encrypted result that, when decrypted, matches the result of operations performed on the plaintext. This repository includes implementations, examples, and documentation on how to utilize HE for secure and private computations.

## Introduction to Homomorphic Encryption

Homomorphic Encryption allows for computations to be carried out on ciphertexts, generating an outcome which, after decryption, corresponds to the operation performed as if it had been executed on the plaintext. This capability is crucial for maintaining privacy and security in cloud computing, data analysis, and other fields where sensitive data may be processed or analyzed by third parties.

## Mathematical Foundations of HE

Homomorphic Encryption is based on complex algebraic structures. Here, we briefly overview the mathematics that enable HE to function, focusing on Fully Homomorphic Encryption (FHE).

### Basics

At its core, HE relies on algebraic structures that support operations on encrypted data. The essential property of an encryption scheme for it to be homomorphic is:

- Let \(\text{Enc}\) represent the encryption function, and \(\text{Dec}\) the decryption function.
- For any operations \( \oplus \) and \( \otimes \) on plaintexts, there exist operations \( \boxplus \) and \( \boxtimes \) on ciphertexts such that:
  
  \[
  \text{Dec}(\text{Enc}(a) \boxplus \text{Enc}(b)) = a \oplus b
  \]

  \[
  \text{Dec}(\text{Enc}(a) \boxtimes \text{Enc}(b)) = a \otimes b
  \]

where \(a\) and \(b\) are plaintexts, and \(\text{Enc}(a)\) and \(\text{Enc}(b)\) are their corresponding ciphertexts.

### Lattice-Based Cryptography

Many FHE schemes are built on lattice-based cryptography. Lattices in cryptography are mathematical structures that can be visualized as points in a multidimensional space. Lattice-based schemes are particularly appealing for FHE due to their resistance to quantum attacks and their mathematical properties that allow for both additive and multiplicative operations on ciphertexts.

### Noise and Bootstrapping

A challenge in HE is managing the "noise" introduced during encryption, which can grow during computations and eventually lead to decryption errors. FHE schemes, such as Gentry's original construction, use a technique called "bootstrapping" to periodically reduce this noise, allowing for an unlimited number of computations.

We also use BFG to get rid of outliers and prep data instead of having to read the data to manually prep it 

## Using the Open FHE Python Wrapper

This section introduces how to use an open-source FHE Python wrapper, providing a simple interface for performing homomorphic operations.

### Installation

```bash
pip install open-fhe-python
```
