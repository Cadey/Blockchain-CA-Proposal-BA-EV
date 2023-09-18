## 1. Introduction

With the rise of blockchain technology, there's an increasing need to verify the authenticity of blockchain addresses associated with established entities. This proposal introduces the Blockchain Address Extended Validation (BA-EV) certificate, aiming to securely link verified entities with their blockchain addresses.

## 2. Objective

To provide a standardized, secure, and verifiable method for entities to associate their identity with specific blockchain addresses, ensuring the entity controls the addresses listed in the certificate.

## 3. Technical Background

### 3.1 X.509 Certificate Structure

X.509 is a standard defining the format of public key certificates. An X.509 certificate contains:

- **Version**: Indicates the X.509 version.
- **Serial Number**: A unique number assigned by the CA to the certificate.
- **Signature Algorithm**: The algorithm used by the CA to sign the certificate.
- **Issuer**: The entity that verifies the information and issues the certificate.
- **Validity**: Start and end dates between which the certificate is valid.
- **Subject**: The entity that the certificate is issued to.
- **Public Key**: The public key of the entity.
- **Extensions**: Additional fields that provide extra information about the certificate.

### 3.2 Certificate Generation Process

1. **Certificate Signing Request (CSR) Creation**: The entity generates a private-public key pair and creates a CSR, which includes the public key and other organizational details.
2. **Submission to CA**: The entity sends the CSR to the CA for signing.
3. **Verification by CA**: The CA verifies the entity's details. For EV certificates, this is an extensive process.
4. **Certificate Issuance**: Once verified, the CA signs the CSR with its private key, creating the certificate.

## 4. Proposed BA-EV Certificate Structure

The BA-EV certificate will extend the standard X.509 certificate with a new extension for blockchain addresses:

- **Blockchain Addresses Extension**:
  - **OID (Object Identifier)**: A unique identifier for this extension.
  - **Critical**: Set to `false`, indicating that systems that don't recognize this extension can safely ignore it.
  - **Value**: An array of key-value pairs:
    - **Network Type**: String (e.g., "XRPL", "Eth", "BTC").
    - **Address**: String (e.g., "khkdshfkdjshfkjdshf" for XRPL, "0x75g547632d4762" for Eth).

## 5. Validation Process

1. **Standard EV Validation**: The CA performs standard identity checks associated with EV validation.
2. **Blockchain Address Verification**: The entity proves ownership or control over each blockchain address they wish to include.
3. **Certificate Generation with Extension**: The CA generates the BA-EV certificate, including the blockchain addresses extension.

## 6. Use Cases

- **NFT Issuance**: Entities can prove that NFTs issued from the addresses in their BA-EV certificate are genuine.
  
- **Smart Contract Deployment**: Organizations can verify that smart contracts deployed from their addresses are legitimate and not malicious replicas.
  
- **Cryptocurrency Transactions**: Businesses can provide assurance to customers and partners that transactions with the addresses in their BA-EV certificate are genuinely associated with them.

## 7. Security Considerations

- **Certificate Transparency**: BA-EV certificates will be logged in public Certificate Transparency (CT) logs, ensuring that any misissuance can be detected.
  
- **Revocation**: If an entity loses control over a blockchain address listed in their BA-EV certificate, they must request the revocation of the certificate. The CA will then issue a new BA-EV certificate after verifying the new set of addresses.

## 8. Conclusion

The introduction of the Blockchain Address Extended Validation (BA-EV) certificate will bridge the gap between traditional web security and the emerging world of blockchain. By providing a verifiable link between entities and their blockchain addresses, we can enhance trust, reduce fraud, and foster more secure interactions in the blockchain ecosystem.

## 9. Call to Action

We urge the CA/Browser Forum to consider this proposal, engage with stakeholders from the blockchain community, and work towards the standardization and issuance of BA-EV certificates.

---

**Note**: This proposal provides a foundational framework for the BA-EV certificate. Further discussions, technical workshops, and stakeholder engagements will be essential to refine the details and address potential challenges.
