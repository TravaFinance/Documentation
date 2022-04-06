# Cross-chain Identification

![Figure 4: Cross-chain identification](<../.gitbook/assets/image (8).png>)

#### User side

Assume that a user would like to confirm her ownership for 3 accounts, the wallet creates a message containing 3 data elements, each includes a pair of a _chainId_ and a _public key_. Every element has a fixed size of 41 bytes: 8 bytes for the _chainId_ and 33 bytes for the _public key_. The data format is as follows:

* data1 (41 bytes) := chainId1 (8 bytes) + pub1 (33 bytes)
* data2 (41 bytes) := chainId2 (8 bytes) + pub2 (33 bytes)
* data3 (41 bytes) := chainId3 (8 bytes) + pub3 (33 bytes)

The wallet uses the Merkle tree to hash the data and obtains the _rootHash_ (32 bytes)

* rootHash := MerkleTree(\[data1,data2,data3]).getRoot()

The user then uses her 3 private keys to sign on the _rootHash_. Each signing creates a signature, named _si_ (64 bytes):

* s1 := Sign(rootHash, prv1)
* s2 := Sign(rootHash, prv2)
* s3 := Sign(rootHash, prv3)

Finally, a transaction is generated and broadcasted to validators. A sample of transaction payload is as follows:

* Type (8 bytes): "SameAs"
* Number (4 bytes): 3 // The number of addresses
* Message (n\*41 bytes): data1 data2 data3
* Signatures (n\*64 bytes): s1 s2 s3
* Timestamp (8 bytes): 1619602364

The total size of a transaction to prove n accounts of the same user is: _20 + n \* 105_ bytes

#### Validator side

Receiving the transaction, TRAVA validators verify the timestamp and then verify the signatures as follows. They first extract the message _{data1, … datan}_ and the list of signatures _{s1, … sn}_. From each data element _datai_, the validators get the _chainId_ and the _public key_ (i.e., _pubi_). They use the Merkle tree to hash the data and regenerate the _rootHash_:

* rootHash := MerkleTree(\[data1, data2, data3]).getRoot()

The validators then use _pubi_ to verify signature _si_ on the rootHash:

* verifySignature(rootHash, s1 , pub1) => valid/invalid
* verifySignature(rootHash, s2 , pub1) => valid/invalid
* verifySignature(rootHash, s3 , pub1) => valid/invalid

Once all signatures are valid, the validators agree that all accounts stored in the message belong to the same user. From n pairs of _chainId_ and _public key_, the validators calculate the respective addresses of the user. To eliminate useless addresses, the validators perform additional checks on the age of the address, its average balance, or the total number of transactions related to the address. Finally, the validators store the _sameAs_ relationship among the valid addresses of the user on the knowledge graph.
