---
title: Cyber Talents Cryptography Challenges 
description: Cryptography Challenges cyber talents, Crack the Hash, RSA101, Guess The Password, Postbase, Hide Data, Hash3rror, UP, LOUDER, Encoding 1, Conjuring.
categories: [CTF]
date: 2024-05-12 11:33:00 +0800
tags: [ctf ,cyber talents]
pin: true
math: true
mermaid: true
image:
  path: "../assets/img/cyber talents cryptography/background.jpg"
  alt: Cryptography challenges from Cyber talents..
---

## Crack the Hash

![Crack the Hash Challenge Image](../assets/img/cyber talents cryptography/Crack the Hash.png)
_Crack the Hash_

First step we need to analyze this hash. We can use <a href="https://www.tunnelsup.com/hash-analyzer/" target="_blank">Hash Analyzer</a> where we found it is an MD5 hash. We can decrypt it by using <a href="https://md5decrypt.net/en/" target="_blank">MD5 Decryptor</a>.

# Solution: 
> Iamtheflag
>

---------------------------------------------------------------------------------------
## RSA101

![RSA101 Challenge Image](../assets/img/cyber talents cryptography/RSA.png)
_RSA101_

After We Extract File we found two file Cipher-Text & Private-Key <img src="../assets/img/cyber talents cryptography/sol-RSA101.png" alt="extraction of RSA101.zip Image"> We will use openssl project to decrypt this cipher: <img src="../assets/img/cyber talents cryptography/solution-RSA1.png" alt="decryption Image">

# Solution: 
> flag{RSA_nice_try}
>

---------------------------------------------------------------------------------------
## Guess The Password

![Guess The Password Challenge Image](../assets/img/cyber talents cryptography/Guess The Pass.png)
_Guess The Password_

step1 we need to analyze this hash. We can use <a href="https://www.tunnelsup.com/hash-analyzer/" target="_blank">Hash Analyzer</a> where we found it is an SHA1 hash. We can decrypt it by using. <a href="https://md5decrypt.net/en/Sha1/" target="_blank">sha-1 Decryptor</a>

# Solution:
> jrahyn+
>

---------------------------------------------------------------------------------------
## Postbase

![Postbase Challenge Image](../assets/img/cyber talents cryptography/Postbase.png)
_Postbase_

First We know the flag format is: flag{xxxxxxxxxxx} ```R[corrupted]BR3tCNDUzXzYxWDdZXzRSfQ==```
we want to fix size to 28-bit. We can use <a href="https://www.tunnelsup.com/hash-analyzer/" target="_blank">Hash Analyzer</a> to know type of hash where we found it is a base64 encoded bruteforce to Reach to format.
<img src="../assets/img/cyber talents cryptography/postbase output.png" alt="bruteforce in text Image">

# Solution:
> flag{B453_61X7Y_4R}
>

---------------------------------------------------------------------------------------
## Hide Data

![Hide Data Challenge Image](../assets/img/cyber talents cryptography/Hide Data.png)
_Hide Data_

After we try rotate alphabets 
<img src="../assets/img/cyber talents cryptography/Hide Data solution.png" alt="ROT13 in text Image">

# Solution:
> 2j68yfhqlz
>

---------------------------------------------------------------------------------------
## Hash3rror

![Hash3rror Challenge Image](../assets/img/cyber talents cryptography/Hash3rror.png)
_Hash3rror_

we have a problem with size fix it to 64-bit by removing two characters not valid ```o``` & ```i``` after that use <a href="https://www.tunnelsup.com/hash-analyzer/" target="_blank">Hash Analyzer</a> where we found it is an SHA256. We can decrypt it by using <a href="https://md5decrypt.net/en/Sha256/" target="_blank">sha-256 Decryptor</a> .
<img src="../assets/img/cyber talents cryptography/sha256-dec.png" alt="sha-256 decryption in text Image">
we found this password ```s3cr3tpassword``` and this note  ```(password = sha-1(hash-result))```
let's encrypt it to ```sha-1``` 
<img src="../assets/img/cyber talents cryptography/sha-1encrypt.png" alt="sha-1 encrypt in text Image">

# Solution: 
> 83874343435092cb681c0d558a84bfeb389c32ed
>  


---------------------------------------------------------------------------------------
## UP

![UP Challenge Image](../assets/img/cyber talents cryptography/UP.png)
_UP_

# Challenge Description :
`Every time you go up you will gain one ballon`
```python
def increment_alphabet_by_index(s):
    result = []
    ignore_chars = {'{', '_'}  # Define ignore characters
    shift = 0
    
    for char in s:
        if char not in ignore_chars:
            shift += 1  # Increment shift for each character except the ignore characters
            
        if char.isalpha():
            if char.islower():
                new_char = chr((ord(char) - ord('a') + shift) % 26 + ord('a'))
            elif char.isupper():
                new_char = chr((ord(char) - ord('A') + shift) % 26 + ord('A'))
        else:
            # For symbols and other characters, do not rotate
            new_char = char
            
        result.append(new_char)
    
    return ''.join(result)

# Example usage:
original_string = "ejxc{T0nY0J_BsUMS4}"
new_string = increment_alphabet_by_index(original_string)
print(new_string)

```
# Solution: 
>flag{Y0uG0T_MeHAH4}
>


---------------------------------------------------------------------------------------
## LOUDER

![LOUDER Challenge Image](../assets/img/cyber talents cryptography/morse code.png)
_LOUDER_

let's Decode Morse code by: <a href="https://morsecode.world/international/decoder/audio-decoder-adaptive.html" target="_blank">Audio decoder</a> .
<img src="../assets/img/cyber talents cryptography/louder output.png" alt="output of decoder Image"> 

Flag format: `flag{X XX XXXXXXXX XXXXXX XXXX XXXXXX}`
# Solution:
> flag{I AM SPEAKING LOUDER THAN BEFORE}
>


---------------------------------------------------------------------------------------
## Encoding 1

![Encoding 1 Challenge Image](../assets/img/cyber talents cryptography/encoding 1.png)
_encoding 1_

We need to analyze this message. by <a href="https://www.tunnelsup.com/hash-analyzer/" target="_blank">Hash Analyzer</a> We found it is an Base64 hash. We can decrypt it by using 
<a href="https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Wm14aFozdGlZWE5sTmpSZmFYTmZiakIwWDNNelkzVnlaWDA9&ieol=CRLF&oeol=CR" target="_blank">Base64 Decode</a>.

# Solution:
 >flag{base64_is_n0t_s3cure}
 >

---------------------------------------------------------------------------------------
## Conjuring

![Conjuring Challenge Image](../assets/img/cyber talents cryptography/Conjuring img.png)
_Conjuring_

`Pigpen Cipher` The Pig Pen Cipher, also known as the Freemason Cipher (or masonic alphabet), is an encryption system that was historically used by some members of Freemasonry to protect their communications. <img src="../assets/img/cyber talents cryptography/conjuring.png" alt="conjuring img Challenge Image">.
<h5>we can decode it from <a href="https://www.dcode.fr/pigpen-cipher" target="_blank"> pigpen-cipher</a> </h5> 

# Solution:
> GHOSTSAREINTHESHELL
>
