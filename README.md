# cyberchef-recipes
A few useful CyberChef recipes.

# SAML Decode

This is the recipe to decode a SAML assertion. The steps are:
1. URL decoding
2. Base64 decoding
3. Decompression
4. XML Format (easier to read)

[https://gchq.github.io/CyberChef/#recipe=URL_Decode()From_Base64('A-Za-z0-9%2B/%3D',true,false)Raw_Inflate(0,0,'Adaptive',false,true)XML_Beautify('%5C%5Ct')](https://gchq.github.io/CyberChef/#recipe=URL_Decode()From_Base64('A-Za-z0-9%2B/%3D',true,false)Raw_Inflate(0,0,'Adaptive',false,true)XML_Beautify('%5C%5Ct'))

# ROT8000

This one is not really a recipe but more of a fun operation that I contributed to the CyberChef project. ROT8000 is a [Caesar cipher](https://en.wikipedia.org/wiki/Caesar_cipher) shifting characters by 8000 in the Unicode charset, the same way [ROT13](https://en.wikipedia.org/wiki/ROT13) shifts latin characters by 13 in the latin alphabet. Also similarly to ROT13, ROT8000 is an involution meaning that if you apply it twice, you end up with the original plaintext message (in other words the ciphering and deciphering functions are the same). A more detailed description of the ROT8000 function can be found on its inventor's [page](https://rot8000.com/info). **This is not encryption nor secure in any way, shape or form! Use it just for fun.**

Coincidently, with ROT8000 latin characters typically end up in the Chinese symbol section of the Unicode charset. So latin text ciphered with ROT8000 looks like Chinese text to a casual observer (unless you can read Chinese and then it's pretty obvious that the text is gibberish). In this recipe you can see an example and if you enable the second ROT8000 function in the recipe you can see how the text gets deciphered back to its original plaintext:

[https://gchq.github.io/CyberChef/#recipe=ROT8000()ROT8000(/disabled)&input=VGhlIHF1aWNrIGJyb3duIGZveCBqdW1wcyBvdmVyIHRoZSBsYXp5IGRvZy4&oenc=65001](https://gchq.github.io/CyberChef/#recipe=ROT8000()ROT8000(/disabled)&input=VGhlIHF1aWNrIGJyb3duIGZveCBqdW1wcyBvdmVyIHRoZSBsYXp5IGRvZy4&oenc=65001)
