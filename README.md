# **Many-time pad attack**

## Problem

Given 11 ciphertexts encrypted with the same otp key, decrypt the target message.

### Approach

* When we XOR 2 ciphertexts together, it will cancel out the keystream so we end up with 2 plaintexts XORed with each other.
* If we XOR the space character with a letter (a-z or A-Z) we will get the same character but with flipped case.
* All of the plaintexts are mostly just letters and spaces so the approach is to xor 2 ciphertexts together and see if any byte in the result is a letter then it's most likely that there will be a space in one of the ciphertexts.
* Repeating this process helped me find a lot of spaces then i just XOR the space with the corresponding byte in the target ciphertext so that we'll get the actual character with flipped case.
* Not all the characters will be correct as there might be other random control characters like colon, semicolon as well but as we traverse those all of those ciphers in many different ways and combine with a lot of guesses the plaintext will be clearer.

**The output file records some of my results when traversing.**

[reference](https://crypto.stackexchange.com/questions/6020/how-to-attack-a-many-time-pad-based-on-what-happens-when-an-ascii-space-is-xor)
