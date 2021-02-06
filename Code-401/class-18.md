## [Encryption, Decryption & Hacking](https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:online-data-security/xcae6f4a7ff015e7d:data-encryption-techniques/a/encryption-decryption-and-code-cracking)

**One of the earliest encryption techniques is the `Caesar Cipher`, invented by Julius Caesar more than two thousand years ago**

---

## Encrypting a message

The `Cesar Cypher` is an alpabetical 6 letter shift of the original letter forward along the alphabet.

```
SECRET MEETING AT THE PALACE
```

```
YKIXKZ SKKZOTM GZ ZNK VGRGIK
```

| CIPHER |  |
| --- | --- |
| Actual Letter| 
| A	B	C	D	E	F	G	H	I	J	K	L	M	N	O	P	Q	R	S	T	U	V	W	X	Y	Z |
| Encrypted Letter |
| G	H	I	J	K	L	M	N	O	P	Q	R	S	T	U	V	W	X	Y	Z	A	B	C	D	E	F |

---

## Decrypting a message

Decrypting a message can only be done if you have a way to know what each letter/number/symbol/icon means. You can either have a simpler `Cesar Cipher` or a more complex cipher that mixes a ton of different letters/numbers/symbols/icons (i.e. looks like someone printed their screen while sleeping on thier keyboard).

## Cracking the cipher

Imagine that a very literate and savvy enemy intercepts one of Caesar's messages.

```
RZ VMZ WMDIBDIB VGG AJMXZN OJ EJDI RDOC XGZJKVOMV OJ YZAZVO OCZ ZIZHT LPZZI VO OCZ IDGZ YZGOV
```

That enemy does not know that Caesar always uses a shift of 3, so he must attempt to "crack" the cipher without knowing the shift.

There are three main techniques he could use: 

- frequency analysis
- known plaintext
- brute force

### Frequency analysis

Human languages tend to use some letters more than others. For example, "E" is the most popular letter in the English language. We can analyze the frequency of the characters in the message and identify the most likely "E" and narrow down the possible shift amounts based on that.

### Known plaintext

Another term for the original unencrypted message is plaintext. If the enemy already knew some part of the plaintext, it will be easier for them to crack the rest of the encrypted version.

### Brute force

> There are only 25 possible shifts (not 26 — why not?). 

The enemy could take some time to try out each of them and find one that yielded a sensible message. They wouldn't even need to try the shifts on the entire message, just the first word or two.

> Even without a computer to assist in decyphering the message, a compitent person could decode a message in under an hour using brute force.....only if they knew that the `Cesar Cipher` was the method of encryption.

- **Encryption**: scrambling the data according to a secret key (in this case, the alphabet shift).
- **Decryption**: recovering the original data from scrambled data by using the secret key.
- **Code cracking**: uncovering the original data without knowing the secret, by using a variety of clever techniques.

Whenever we consider a possible encryption technique, we need to think about all those aspects:
-  how easy is it to encrypt?
-  how easy is it to decrypt? 
-  how easy is it for a nefarious individual to crack the code?


## [Ceasar Cipher](https://en.wikipedia.org/wiki/Caesar_cipher)

The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the scheme, A → 0, B → 1, ..., Z → 25.[2] Encryption of a letter x by a shift n can be described mathematically as,[3]

E<sub>n</sub>(x)=(x+n) mod {26}

Decryption is performed similarly,

D<sub>n</sub>(x)=(x-n) mod {26}

> Quickest current way that I can figure to decypher the text is to return a list of 25 versions that do not match the original, shifted 1 letter per iteration.

The [Vigenère cipher](https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher) uses a Caesar cipher with a different shift at each position in the text; the value of the shift is defined using a repeating keyword. If the keyword is as long as the message, is chosen at random, never becomes known to anyone else, and is never reused, this is the one-time pad cipher, proven unbreakable. The conditions are so difficult they are, in practical effect, never achieved. Keywords shorter than the message (e.g., "Complete Victory" used by the Confederacy during the American Civil War), introduce a cyclic pattern that might be detected with a statistically advanced version of frequency analysis.[13]

### Breaking the cipher

The Caesar cipher can be easily broken even in a ciphertext-only scenario. Two situations can be considered:

an attacker knows (or guesses) that some sort of simple substitution cipher has been used, but not specifically that it is a Caesar scheme;
an attacker knows that a Caesar cipher is in use, but does not know the shift value.

## [Cryptography Crash Course](https://www.youtube.com/watch?v=jhXCTbFnK8o)

Computers are never secure, they are only protected to a certain extent.

Cryptography = Crypto + Graphy = Secret Writing

Cryptanalyst = Person tasked with decoding encrypted messages/information




## Additional Resources
- [Introduction to Cryptography](https://thebestvpn.com/cryptography/)
- [How Computers Generate Random Numbers](https://www.howtogeek.com/183051/htg-explains-how-computers-generate-random-numbers/)