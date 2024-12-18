# Challenge Description

We just freaky like that!

Author: xenon, Wixter_07

Points: 95

Category: OSINT
# My Solve

Looking at the metadata of the attachment provided we get a encrypted text under `subject` which followed `monoalphabetic substitution cipher`. Decrypting this we get a link `HTTPS://BIT.LY/FREAKESTEIN0` in the decrypted text. This redirects us to another image `ducky.png`. Extracting ducky.png we get a file `secret.txt` which contains the link to a github account for the account `freakada-3301`. In the `README` of the only repo under the account we are given a sort of encrypted part of our flag- `1sk3vr3d_qw5yvvc}`

Looking at the commit history of the repo we see a large chunk of text along with a bunch of numbers in the format `x:y:z` where x is the line, y is the word and z is the character, a standard `book cipher`. Following this decryption logic we get a invite link to a discord server. 

After joining this discord server there is a bot named `freakada` which asks for a `prime`. Entering `3301`, the bot prompts us for the product of three prime numbers `3301*x*y` where x and y are assosciated with the original atttachment. After looking back at the original image the two numbers were `449` and `503` which were prime and were the width and height of the image. Multiplying them we get the answer `745520947`. The bot gives us coordinates to a location after entering the answer.

This location is named `Freaky Backshots Cliff` (very freaky indeed). We can see a QR code in aa bunch of images of the location. Following the qr code downloads a `wav` file. Now putting the `wav` in a morse code decoder we get the first part of the flag `nite{4_wannabe_`. But we are given additional info too. The audio message says `Here is a free key`. 

With  this info i opened a vignere cipher decoder with the key `freekey` and decoded the encrypted flag we got in the github repo and got `1nt3rn3t_my5tery}` which seems to be the 2nd part of the flag.

Now combining the 2 parts we get our complete flag: `nite{4_wannabe_1nt3rn3t_my5tery}`.
