# Deep
Solution to EkoParty 2020 Pre-CTF Challenge - Deep

### Problem

Where is the flag?
Attachment File: Deep


### Solution

When you do a bin dump of the file you get the "JFIF" Header that means its a JPEG image. So when you open as image you see a photo with a binary code. If you convert that binary to ASCII you will get a phrase that ITS NOT THE FLAG. So the next step is to do some stego over the image.

Using a tool like [steghide](https://futureboy.us/stegano/decinput.html) without a password, you can extract a file "flag.enc" that was embeed on the image.

If you open that file as text you will see an encrypted string. Using a [cipher detector](https://www.boxentriq.com/code-breaking/cipher-identifier) you get that is Base64. Using a string Base64 decoder you will see that its not simple text instead is another file (image) encrypted. Using this [tool](https://base64.guru/converter/decode/file) you can decode files in Base64.

When you get the new image, again, using Stego but this time with a password (the phrase that you got on the start) you will get the file "flag.txt" with the flag inside.

