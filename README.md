# cyberchef-recipes

A few useful CyberChef recipes.

## JWT Decode

This is the recipe to decode a JWT token. The steps are:

1. URL decoding
2. Base64 decoding (for each section)
3. Remove the signature blob
4. JSON formating (easier to read)

[Try it!](<https://gchq.github.io/CyberChef/#recipe%3DURL_Decode%28%29Fork%28%27.%27%2C%27%255C%255
Cn%27%2Cfalse%29From_Base64%28%27A-Za-z0-9%252B%2F%253D%27%2Ctrue%2Cfalse%29Filter%28%27Line%2520fe
ed%27%2C%27%255E%257B.%2A%257D%24%27%2Cfalse%29JSON_Beautify%28%27%2520%2520%2520%2520%27%2Cfalse%2
Ctrue%29&input=ZXlKaGJHY2lPaUpJVXpJMU5pSXNJblI1Y0NJNklrcFhWQ0o5LmV5SnpkV0lpT2lJeE1qTTBOVFkzT0Rrd0lp
d2libUZ0WlNJNklrcHZhRzRnUkc5bElpd2lhV0YwSWpveE5URTJNak01TURJeWZRLlNmbEt4d1JKU01lS0tGMlFUNGZ3cE1lSmY
zNlBPazZ5SlZfYWRRc3N3NWM>)

[jwt.io](https://jwt.io/) is probably a better alternative but the
above recipe can be a starting point if you're going to do further
operations on the decoded JWT.

## SAML Decode

This is the recipe to decode a SAML assertion. The steps are:

1. URL decoding
2. Base64 decoding
3. Decompression
4. XML formating (easier to read)

[Try it!](https://gchq.github.io/CyberChef/#recipe=URL_Decode%28%29From_Base64%28%27A-Za-z0-9%252B%
2F%253D%27%2Ctrue%2Cfalse%29Raw_Inflate%280%2C0%2C%27Adaptive%27%2Cfalse%2Ctrue%29XML_Beautify%28%2
7%255C%255Ct%27%29&input=aFpKQmI5c3dESVglMkZpcWE3N2RobzBreUlVMlFOaWdib05xOXhkOWhsa0dXbTFpcExzU2pGN2
IlMkJ2N0tSYmh3SFpsU0slMkZSNzNIeGRWenE4Z0JMRXFqYzVyR0UwcEFDMU5MJTJGWmpUaCUyRkltbXRPcjVRSjVxN0k5VzNuW
DZIdm9QS0FqWVZBak83N2sxRnZOREVlSlRQTVdrRG5CdHF2UGR5eUxKMnh2alRQQ0tFcFdpR0Jka0xvMkduMExkZ3YySUFVODNO
JTJGbHRIRnVqeXhKZUZDSkc4OTdrRUlaWDhmQ3RHUFJ5MlNRU3did1B5UksxbUVycWJrYmZ6TEFBcXZwWGFqRzA3U0hhdVQ0TUp
hRWhXb3ZYRExpRXdIYWVmdVNnTUFQeWp4S2ZkdkhYQXdZU202TUZUQiUyQk82YzdyaEFvMmF4eiUyQnRNMTJaT3FaN3JyZURkVD
FhSHFVOUYxVDVXcXMlMkZZU20xOVRlZmtjV3JIZ2lQSUFmNFlSUFd3ME9xNWRUck5KT28lMkZTTk1wbTVlUWpTMU0ybmNjWEY3T
WZsQlFueXo1SmZZemluTCUyRlZzUW5aYlZrV1VmRjFXMUx5JTJGUzNTMEVCUEFiSlIzYjVQN2p5WXY1bE1sMmZEV1NUdiUyQmIl
MkZQNVVzQWJ0YUZVVks4a0pWU3ByJTJCMndGMXd3MWtQbzdrdGQlMkJkWEdDcXlqblpqSzNPV2E1UWhMMHEyeFlEJTJGNXJtU09
3bjJQJTJCZERrJTJCVnB5YiUyQnZlUGtL)

## AWS Log Event

This is the recipe to decode a raw AWS Log Event. The steps are:

1. Base64 decoding
2. Decompression
3. JSON formating (easier to read)

[Try it!](https://gchq.github.io/CyberChef/#recipe%3DFrom_Base64%28%27A-Za-z0-9%252B%2F%253D%27%2Cfa
lse%2Cfalse%29Gunzip%28%29JSON_Beautify%28%27%2520%2520%2520%2520%27%2Cfalse%2Ctrue%29&input=SDRzSUF
GUnBtbWdBLzVXUVQwK0VNQkRGdjh1Y01aYi83dDZxRkx6c2lUMXBOZzNxUUpwUVN0cWlNWVR2emxnMUdtL2VwdS8zT24xOUsyaDB
yaHZ3L0Q0akhLSGlaeTVQb20xNUl5QUM4emFoSlRsTzBpd3Z5cHNEaXhPU1J6TTAxaXd6RVdjMFNqckxJUWlCdGQ1aXB3aytrUDN
uNHRkMHpXL3ZLbEZmTmZma2RzdVRlN1pxOXNwTXRSbzlXZ2ZIeDgrdHY1bnNBNFJMZUVDODR1US9qQ3VvbHoveC9qTlJBSytvQU4
5cCtrdGM1dGtoSzlLMFlJeEYzOFhRK3Q0WTJDN2JEbHc0aGQ4c0FRQUE)

## ROT8000

This one is not really a recipe but more of a fun operation that I
contributed to the CyberChef project. ROT8000 is a [Caesar
cipher](https://en.wikipedia.org/wiki/Caesar_cipher) shifting
characters by 8000 in the Unicode charset, the same way
[ROT13](https://en.wikipedia.org/wiki/ROT13) shifts latin characters
by 13 in the latin alphabet. Also similarly to ROT13, ROT8000 is an
involution meaning that if you apply it twice, you end up with the
original plaintext message (in other words the ciphering and
deciphering functions are the same). A more detailed description of
the ROT8000 function can be found on its inventor's
[page](https://rot8000.com/info). **This is not encryption nor secure
in any way, shape or form! Use it just for fun.**

Coincidently, with ROT8000 latin characters typically end up in the
Chinese symbol section of the Unicode charset. So latin text ciphered
with ROT8000 looks like Chinese text to a casual observer (unless you
can read Chinese and then it's pretty obvious that the text is
gibberish). In this recipe you can see an example and if you enable
the second ROT8000 function in the recipe you can see how the text
gets deciphered back to its original plaintext:

[Try it!](<https://gchq.github.io/CyberChef/#recipe%3DROT8000%28%29ROT8000%28%2Fdisabled%29&input=VG
hlIHF1aWNrIGJyb3duIGZveCBqdW1wcyBvdmVyIHRoZSBsYXp5IGRvZy4&oenc=65001>)
