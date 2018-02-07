# RadPad
A simple protocol for low-tech, future-proof, unbreakable encryption based on the One Time Pad and Diffie-Hellman Key Exchange.

The RadPad is a protocol for mathematically unbreakable encryption which is infinitely sustainable. Unbreakability comes from the One Time Pad and sustainability comes from the Diffie-Hellman Key Exchange.

The Caesar Chiper is a simple method of encryption in which all characters in a message are changed to another letter in the character space, including themselves, by a set amount called the Shift. Caesar Ciphers are easy to crack by a variety of methods. The One Time Pad (OTP) operates much like the Caesar Cipher but by shifting each letter of the message by a truly random number of equal probability from 1 to the total number of characters in the character space, the message is completely unbreakable. The key for a Caesar Cipher is a single number but the OTP requires a key for each character of the message. It is common to create a list of Shifts which can be distributed to other parties but this list cannot be repeated and will therefore eventually be used up. Any list or replacement list must be kept and exchanged with absolute privacy which is often impossible.

The Diffie-Hellman Key Exchange (DHKE) allows for private, sustainable key exchange by allowing each party to randomly select a Private Key which can never be shared, compute a Public Key which can be shared over insecure channels with no risk, and compute a Shared Key which can be used as a Shift in a given cipher protocol. For a Caesar Cipher this would be the last step but the One Time Pad requires a key for each character in the message to be encoded and those keys but be equal in probability from 1 to the total number of characters in the character space. The original DHKE does not return Shifts of equal probability or distribution and cannot be used with the OTP.

Enter the RadPad. By modifying the calculations which generate the Shifts and placing mild constraints on the character space length and Key generation, equal probability and distribution is guaranteed. The RadPad is a minimal protocol which defines these constraints. The OTP unbreakability can now be used infinitely without ever having to meet the other party.

To apply the RadPad Protocol: (See the Python code for a simpler explanation.)
  1) Determine P, a prime number which is 1 greater than the total number of characters in the character space. Modify the character space or find a more suitable prime if necesary.
  2) Determine R, a primitive root of P. Table provided below.
  3) Private Keys, as defined by the original DHKE, are found by independently selecting 2 numbers from 1 to the total number of characters in the character space by truly random means and adding the results.
  4) Compute Public Keys as defined by the original DHKE.
  5) Compute the Shift by raising R to the power of your Private Key, multiplying that by the other party's Public Key, and applying P as the Modulus.
  
The RadPad relies not on massive Primes like the DHKE but in the equal probability of all outcomes of a given length. Message encryption and decryption requires Public Keys which require Private Keys. Every possible combination of Private Key selection is equally likely. Every Public Key possible is equally likely. A given Public Key has a probability of tracing back to the Private Key which generated it equal to 1/length of characters in the character space squared but it is impossible to know if this guess is correct since all outcomes are equally likely. Every Shift possible is equally likely. Finally, every possible encrypted character is equally likely and has no impact on the other character. Simply put, any message of a given length is equally likely to be any other message of a given length it is impossible to know which is correct without a correct Private Key.

This is what makes the RadPad so rad. No amount of computational power can make any improvement over a guess. The length of the keys is determined by the key space, not the time required to break down massive prime numbers. It is truly unbreakable, future-proof, and low-tech to the point that any calculator with a MOD function is enough. If your character space consists of a 1 and 0, as found in binary, you could easily perform these calculations by hand. David and Goliath in purest form.
  
The following list can be used as to determine P, R. Many values for P have multiple values for R, only the lowest is listed here. 3, 2. 5, 2. 7, 3. 9, 2. 11, 2. 13, 6. 16, 5. 17, 10. 19, 10. 23, 10. 25, 2. 27, 2. 29, 10. 31, 17. 32, 5. 37, 5. 41, 6. 43, 28. 47, 10. 49, 10. 53, 26. 59, 10. 61, 10. 64, 5. 67, 12. 71, 62. 73, 5. 79, 29. 81, 11. 83, 50. 89, 30. 97, 10.
  
Rather than primes alone, it may be possible to use arbitrary numbers if the required equal distribution can be achieved. Primes and Primitive Roots guarantee this distribution so the RadPad currently limits P and R until distribution with arbitrary numbers can be likewise guaranteed. Several theories show hope for an answer.
  
It may be useful to use the same character space multiple times in order to find a convenient value for P. Any characters may be used in the character space so long as they do not repeat unequally.
  
The RadPad is the minimal protol to achieve the desired result and lends itself to a wide range of applications. It is itself perfectly secure and unbreakable but this is not automatically true of applications which utilize it. While the Public Keys and encrypted messages may be sent by any means desired, it is up to the application and/or the user to confirm the identity of the other party. Likewise, Parties may choose to exchange a message one character at a time preceeded by the exchange of a single Public Key in each direction or they may wish to first exchange a list of arbitrary length which is followed by the encrypted message. It is also possible to communicate with more than 2 parties. The RadPad is the pure core upon which applications are built, nothing more.
