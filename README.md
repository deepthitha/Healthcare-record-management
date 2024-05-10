# Healthcare-record-management
This project is aimed to create a cloud based platform integrating blockchain technology for secure management of patient and doctor records. Enables separate storage for patient and doctor data, ensuring data integrity and privacy while facilitating efficient record management and retrieval


1. Blockchain Basics:
   - Blockchain is a publicly-managed record of transactional data.
   - Data blocks are ordered chronologically and connected to form a chain.
   - Old blocks of data are permanent and cannot be retroactively modified.

2. Role of Full Nodes:
   - Blockchain networks rely on full nodes to store, verify, and distribute the full set of data.
   - Full nodes maintain the history of all past transactions.

3. Immutability:
   - Blockchains are advertised as immutable, meaning data cannot be changed or erased once posted.

4. Encryption and Hashing:
   - Data in the blockchain can be stored in encrypted form using encryption and hashing methods.
   - Only users with the correct key can access the content of the blockchain.

5. Off-Chain Work:
   - To achieve encrypted storage, some work is done off-chain, outside the blockchain.
   - A third-party centralized system is created to ensure privacy.

6. Centralized Third-Party System:
   - The third-party system stores a unique key for the data, such as patient data.
   - Even the third-party system cannot access the data stored in the blockchain, despite holding the key.

COMPONENTS:
Blockchain - to store data securely in block formats implemented by using Ethereum
Crypting algorithms - SHA-256 or anyother can be used 

WORKING:

Encryption, Hashing, and Storage Process:

     Storing Encrypted Data in the Blockchain:
- Client generates a key using the data as key-text and encrypts the data locally using AES encryption.
- Encrypted data is sent to the Third Party System, which further encrypts it using SHA-256 to generate a key and encrypts the locally encrypted data.
- The generated key is stored in the Third Party System's database along with the owner's ID.
- Encrypted data from the Third Party System, along with the locally generated key, is sent to the Blockchain.
- The Blockchain writes this transaction into a block, making the new encrypted data immutable across the network.

      Fetching Encrypted Data from the Blockchain:
- Encrypted data and the locally generated key are fetched from the Blockchain.
- Encrypted data is sent to the Third Party System, which decrypts it using the stored key associated with the user ID, only if permission is granted by the data owner.
- Decrypted data is sent back to the Client.
- The decrypted data from the Third Party System is then decrypted using the key fetched from the Blockchain to retrieve the original data.

This process ensures secure storage and retrieval of data while maintaining privacy and immutability through encryption, hashing, and the involvement of a third-party system.

CONCLUSION:


1. Challenges with Immutable Data:
   - In a blockchain, data is immutable once it's written, posing challenges for scenarios where data needs to be deleted or access restricted.

2. Double Encryption Method:
   - Original data is encrypted twice: first locally by the client, then by the Third Party System.
   - This double encryption ensures that even if someone accesses the blockchain, the encrypted data remains incomprehensible.

3. Data Deletion Process:
   - If a user wishes to delete their data from the blockchain, all associated keys used for decryption are deleted.
   - Without the decryption keys, the encrypted data becomes meaningless random bits, rendering it useless for any purpose.

4. Privacy Enhancement:
   - This method enhances privacy within the blockchain by making data unreadable to unauthorized parties.
   - Users have control over their data, being able to delete it from the blockchain when needed.

5. Benefits:
   - Provides a level of privacy within the blockchain, addressing concerns about data visibility and access control.
   - Enables users to manage their data, including deletion, while maintaining the integrity of the blockchain's immutable ledger.

