# History
- Julius Caesar had a system of ciphering vital information that was to be relayed to his generals. It is called the Caesar Cypher. (Remember CS50 problem set) More on this [[|later]].
- In the prehistoric times a person would draw a message on a bald head and let the hair grow. This sort of hid the message.
# Secure Communication
In the basic scenario there are two parties. *Alice* and *Bob* and suppose *Eve* is a potential eavesdropper.

When *Alice* sends a message (the original string is called **plaintext**) to bob, she *encrypts* it using a method arranged with *Bob*. It should be assumed that the encryption method is known to *Eve*; what keeps the message secret is a **key**. The encrypted message(known as **cyphertext**), he *changes* it back to *plaintext* using the key.

![[IMG_20240729_115846930~2.jpg|600]]
**Possible Goals**:
	1. Read the message
	2. Find the key and thus read all messages encrypted with that key.
	3. Corrupt Alice's message into another message in such a way that Bob will think Alice sent the altered message.
	4. Masquerade as Alice, and thus communicate with Bob even though Bob believes that he is talking to alice.
Case (3) and (4) relate to issues of integrity and authentication.
A more active and malicious adversary corresponding to cases (3) and (4), is sometimes called **Mallory** in the literature.
More passive observers (as in cases (1) and (2)) are sometimes named **Oscar**.

## Possible Attacks
There are 4 main types of attacks

### Cypthertext only
*Eve* has only a copy of the cypthertext

### Known plaintext
*Eve* has the copy of the cyphertext and the corresponding plaintext. If she can deduce the decryption key and if *Alice* doesn't change the key, *Eve* can read all future messages.
For many weak cryptosystems, this suffices to find the **key**. Even for stronger systems such as the German Enigma machine used in WWII, this amount of information has been useful.

### Chosen Plaintext:
Eve gains temporary access to the encryption machine. She can open it to find the key; however she can encrypt a large number of suitably chosen plaintexts and try to use the resulting ciphertexts to deduce the key.

**It could happen as follows**:
Suppose we want to identify whether an airplane is friend or foe. We can do this by sending a random message to the plane, which encrypts the message automatically and sends it back. Only the Friendly plane is assumed to have the correct key. Compare the message received with the correctly encrypted message. If they match the plane is a friend, if they don't the plane is a foe. 

However, an enemy can send a large number of messages to the plane and look at the cyphertext. If this allows them to deduce the key, they can masquerade as friendly and easily infiltrate.
### Chosen cyphertext
Eve obtains temporary access to the decryption machine, uses it to "decrypt" several strings of symbols, and tries to use the results to deduce the key.
