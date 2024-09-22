# cyberchef-recipes

A few useful CyberChef recipes.

# JWT Decode

This is the recipe to decode a JWT token. The steps are:

1. URL decoding
2. Base64 decoding (for each section)
3. Remove the signature blob
4. JSON formating (easier to read)

[Try it!](<https://gchq.github.io/CyberChef/#recipe=URL_Decode()Fork('.','%5C%5Cn',false)From_Base64('A-Za-z0-9%2B/%3D',true,false)Filter('Line%20feed','%5E%7B.*%7D$',false)JSON_Beautify('%20%20%20%20',false,true)&input=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c>)

[jwt.io](https://jwt.io/) is probably a better alternative but the above recipe can be a starting point if you're going to do further operations on the decoded JWT.

# SAML Decode

This is the recipe to decode a SAML assertion. The steps are:

1. URL decoding
2. Base64 decoding
3. Decompression
4. XML formating (easier to read)

[Try it!](<https://gchq.github.io/CyberChef/#recipe=URL_Decode()From_Base64('A-Za-z0-9%2B/%3D',true,false)Raw_Inflate(0,0,'Adaptive',false,true)XML_Beautify('%5C%5Ct')&input=hZJBb9swDIX%2Fiqa77dho0kyIU2QNigboNq9xd9hlkGWm1ipLsSjF7b%2Bv7KRbhwHZlSK%2FR73HxdVzq8gBLEqjc5rGE0pAC1NL%2FZjTh%2FImmtOr5QJ5q7I9W3nX6HvoPKAjYVAjO77k1FvNDEeJTPMWkDnBtqvPdyyLJ2xvjTPCKEpWiGBdkLo2Gn0Ldgv2IAU83N%2FltHFujyxJeFCJG897kEIZX8fCtGPRy2SQSwbwPyRK1mErqbkbfzLAAqvpXajG07SHauT4MJaEhWovXDLiEwHaefuSgMAPyjxKfdvHXAwYSm6MFTB%2BO6c7rhAo2axz%2BtM12ZOqZ7rreDdT1aHqU9F1T5Wqs%2FYSm19TefkcWrHgiPIAf4YRPWw0Oq5dTrNJOo%2FSNMpm5eQjS1M2nccXF7MflBQnyz5JfYzinL%2FVsQnZbVkWUfF1W1Ly%2FS3S0EBPAbJR3b5P7jyYv5lMl2fDWSTv%2Bb%2FP5UsAbtaFUVK8kJVSpr%2B2wF1ww1kPo7ktd%2BdXGCqyjnZjK3OWa5QhL0q2xYD%2F5rmSOwn2P%2BdDk%2BVpyb%2BvePkK>)

# ROT8000

This one is not really a recipe but more of a fun operation that I contributed to the CyberChef project. ROT8000 is a [Caesar cipher](https://en.wikipedia.org/wiki/Caesar_cipher) shifting characters by 8000 in the Unicode charset, the same way [ROT13](https://en.wikipedia.org/wiki/ROT13) shifts latin characters by 13 in the latin alphabet. Also similarly to ROT13, ROT8000 is an involution meaning that if you apply it twice, you end up with the original plaintext message (in other words the ciphering and deciphering functions are the same). A more detailed description of the ROT8000 function can be found on its inventor's [page](https://rot8000.com/info). **This is not encryption nor secure in any way, shape or form! Use it just for fun.**

Coincidently, with ROT8000 latin characters typically end up in the Chinese symbol section of the Unicode charset. So latin text ciphered with ROT8000 looks like Chinese text to a casual observer (unless you can read Chinese and then it's pretty obvious that the text is gibberish). In this recipe you can see an example and if you enable the second ROT8000 function in the recipe you can see how the text gets deciphered back to its original plaintext:

[Try it!](<https://gchq.github.io/CyberChef/#recipe=ROT8000()ROT8000(/disabled)&input=VGhlIHF1aWNrIGJyb3duIGZveCBqdW1wcyBvdmVyIHRoZSBsYXp5IGRvZy4&oenc=65001>)
