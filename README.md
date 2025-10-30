# cyberchef-recipes

A few useful CyberChef recipes.

## JWT Decode

This is the recipe to decode a JWT token. The steps are:

1. URL decoding
2. Base64 decoding (for each section)
3. Remove the signature blob
4. JSON formating (easier to read)

[Try it!](<https://gchq.github.io/CyberChef/#recipe=URL_Decode(true)Fork('.','%5C%5Cn',false)From_Base64('A-Za-z0-9%2B/%3D',true,false)Filter('Line%20feed','%5E%7B.*%7D$',false)JSON_Beautify('%20%20%20%20',false,true)&input=ZXlKaGJHY2lPaUpJVXpJMU5pSXNJblI1Y0NJNklrcFhWQ0o5LmV5SnpkV0lpT2lJeE1qTTBOVFkzT0Rrd0lpd2libUZ0WlNJNklrcHZhRzRnUkc5bElpd2lhV0YwSWpveE5URTJNak01TURJeWZRLlNmbEt4d1JKU01lS0tGMlFUNGZ3cE1lSmYzNlBPazZ5SlZfYWRRc3N3NWM>)

[jwt.io](https://jwt.io/) is probably a better alternative but the
above recipe can be a starting point if you're going to do further
operations on the decoded JWT.

## SAML Decode

This is the recipe to decode a SAML assertion. The steps are:

1. URL decoding
2. Base64 decoding
3. Decompression
4. XML formating (easier to read)

[Try it!](<https://gchq.github.io/CyberChef/#recipe=URL_Decode(true)From_Base64('A-Za-z0-9%2B/%3D',true,false)Raw_Inflate(0,0,'Adaptive',false,true)XML_Beautify('')Syntax_highlighter('auto%20detect')&input=aFpKQmI5c3dESVglMkZpcWE3N2RobzBreUlVMlFOaWdib05xOXhkOWhsa0dXbTFpcExzU2pGN2IlMkJ2N0tSYmh3SFpsU0slMkZSNzNIeGRWenE4Z0JMRXFqYzVyR0UwcEFDMU5MJTJGWmpUaCUyRkltbXRPcjVRSjVxN0k5VzNuWDZIdm9QS0FqWVZBak83N2sxRnZOREVlSlRQTVdrRG5CdHF2UGR5eUxKMnh2alRQQ0tFcFdpR0Jka0xvMkduMExkZ3YySUFVODNOJTJGbHRIRnVqeXhKZUZDSkc4OTdrRUlaWDhmQ3RHUFJ5MlNRU3did1B5UksxbUVycWJrYmZ6TEFBcXZwWGFqRzA3U0hhdVQ0TUphRWhXb3ZYRExpRXdIYWVmdVNnTUFQeWp4S2ZkdkhYQXdZU202TUZUQiUyQk82YzdyaEFvMmF4eiUyQnRNMTJaT3FaN3JyZURkVDFhSHFVOUYxVDVXcXMlMkZZU20xOVRlZmtjV3JIZ2lQSUFmNFlSUFd3ME9xNWRUck5KT28lMkZTTk1wbTVlUWpTMU0ybmNjWEY3TWZsQlFueXo1SmZZemluTCUyRlZzUW5aYlZrV1VmRjFXMUx5JTJGUzNTMEVCUEFiSlIzYjVQN2p5WXY1bE1sMmZEV1NUdiUyQmIlMkZQNVVzQWJ0YUZVVks4a0pWU3ByJTJCMndGMXd3MWtQbzdrdGQlMkJkWEdDcXlqblpqSzNPV2E1UWhMMHEyeFlEJTJGNXJtU093bjJQJTJCZERrJTJCVnB5YiUyQnZlUGtL>)

## AWS Log Event

This is the recipe to decode a raw AWS Log Event. The steps are:

1. Base64 decoding
2. Decompression
3. JSON formating (easier to read)

[Try it!](<https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',false,false)Gunzip()JSON_Beautify('%20%20%20%20',false,true)&input=SDRzSUFGUnBtbWdBLzVXUVQwK0VNQkRGdjh1Y01aYi83dDZxRkx6c2lUMXBOZzNxUUpwUVN0cWlNWVR2emxnMUdtL2VwdS8zT24xOUsyaDByaHZ3L0Q0akhLSGlaeTVQb20xNUl5QUM4emFoSlRsTzBpd3Z5cHNEaXhPU1J6TTAxaXd6RVdjMFNqckxJUWlCdGQ1aXB3aytrUDNuNHRkMHpXL3ZLbEZmTmZma2RzdVRlN1pxOXNwTXRSbzlXZ2ZIeDgrdHY1bnNBNFJMZUVDODR1US9qQ3VvbHoveC9qTlJBSytvQU45cCtrdGM1dGtoSzlLMFlJeEYzOFhRK3Q0WTJDN2JEbHc0aGQ4c0FRQUE>)

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

[Try it!](<https://gchq.github.io/CyberChef/#recipe=ROT8000()ROT8000(/disabled)&input=VGhlIHF1aWNrIGJyb3duIGZveCBqdW1wcyBvdmVyIHRoZSBsYXp5IGRvZy4&oenc=65001>)

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## Security

Please read [SECURITY.md](SECURITY.md) for details on our security policy and how to report security vulnerabilities.

## Code of Conduct

Please read [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for details on our code of conduct.

## License

This project is licensed under the terms of the [LICENSE](LICENSE) file.
