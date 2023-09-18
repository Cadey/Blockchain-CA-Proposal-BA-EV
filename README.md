# Blockchain Address Extended Validation (BA-EV) Certificate Proposal

## 1. Introduction

With the rise of blockchain technology and its integration into various sectors, there's an increasing need to verify the authenticity of blockchain addresses associated with established entities. This proposal introduces a new type of certificate, the Blockchain Address Extended Validation (BA-EV) certificate, which aims to link verified entities with their blockchain addresses securely.

## 2. Objective

To provide a standardized, secure, and verifiable method for entities to associate their identity with specific blockchain addresses, ensuring that the entity in question controls the addresses listed in the certificate.

## 3. Certificate Details

- **Name**: Blockchain Address Extended Validation (BA-EV) Certificate
- **Validation Level**: Extended Validation, following the rigorous identity checks of standard EV certificates.
- **Unique Feature**: Contains an array of blockchain addresses and their corresponding network types.

## 4. Certificate Structure

The BA-EV certificate will include:

- All standard fields present in a typical EV certificate, such as:
  - `Common Name (CN)`
  - `Organization (O)`
  - `Organizational Unit (OU)`
  - `Country (C)`
  - `State (ST)`
  - `Locality (L)`
  - `Serial Number`
  - `Validity Period`
  - `Issuer`
  - `Signature Algorithm`
  - `Public Key`

- A new field named `Blockchain Addresses`:
  - Data Type: Array of Objects
  - Each object will consist of:
    - **Network Type**: String (e.g., "XRPL", "Eth", "BTC")
    - **Address**: String (e.g., "khkdshfkdjshfkjdshf" for XRPL, "0x75g547632d4762" for Eth)

## 5. Validation Process

1. **Standard EV Validation**: The Certificate Authority (CA) will perform all standard identity checks associated with EV validation. This includes verifying the entity's legal, physical, and operational existence.
  
2. **Blockchain Address Verification**: 
   - The entity must prove ownership or control over each blockchain address they wish to include in the certificate.
   - This can be achieved by signing a message provided by the CA using the private key associated with the blockchain address or by making a microtransaction to an address specified by the CA.

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
