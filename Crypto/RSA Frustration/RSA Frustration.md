## Challenge Name: RSA Frustration
Category: **Crypto**  
Difficulty: **Hard**  
Points: **499**  
Solves: **12**

Challenge Description: 
My friend encrypted the flag but realized they can’t decrypt it. Frustrated, they decided to keep encrypting the flag hoping this will somehow fix it. How are we going to recover it now? An efficent solution would probably be useful here.

### Files
```
from Crypto.Util.number import getPrime, bytes_to_long, long_to_bytes

def encrypt(numToEncrypt):
    def getPrimeCustom(bitLength, e):
        while True:
            i = getPrime(bitLength)
            if (i-1) % e**2 == 0:
                return i

    global e
    global C
    bitLength = ((len(bin(numToEncrypt)) - 2) // 2) + 9
    e = 113
    p = getPrimeCustom(bitLength, e)
    q = getPrimeCustom(bitLength, e)
    N = p * q
    print(f"N = {N}")
    C = pow(numToEncrypt, e, N)
    return C

msg = b"wsc{????????????????????}"
numToEncrypt = bytes_to_long(msg)

# maybe if I keep encrypting it will fix itself???
# surely it won't make it worse
encryptedNum = encrypt(numToEncrypt)
for x in range(26):
    encryptedNum = encrypt(encryptedNum)
  
print(f"e = {e}")
print(f"C = {C}")
```

[RSA_Frustration output](https://github.com/drewd314/WolvSec-CTF-2022-Writeups/files/8358502/RSA_Frustration_-_output.2.txt)

### Approach
The idea for this challenge stemmed from [Dice CTF's](https://ctftime.org/writeup/32264) recent RSA challenge!

Based off the description, the person is having trouble decrypting their flag. This means something is broken with the algorithm. We can see that the encryption script is choosing primes that are divisible by the second power of e, meaning phi is not coprime to e!. This will cause a decryption using the inverse mod of the ciphertext to not be useful.

Therefore, we have to use a solution similar to [Dice CTF's](https://ctftime.org/writeup/32264) where we take all cadidite decryptions using the nth_root algorithm in sage.



#Step 1:
  
If you run strings on the file, it will output hidden comments:
![22103aa00aedae679sss47c30b74cbd204e](https://user-images.githubusercontent.com/74334127/160298238-9769a267-43fc-4d3b-b447-b86baff1a6d6.png)

This is hinting that you will need to view this as a raw file in photoshop. This is also hinted in the description with RAW being capitalized. To convert it to a raw file, change the file extention from ".wav" to ".raw". Then, when trying to open the file in photoshop you are preseneted with the following options:

  ![](https://user-images.githubusercontent.com/74334127/160299927-56c70db3-7c64-43a4-8dfc-5995f85c8c30.png)
  
From the hint, we are given that the channels should be set to 1 and the depth should be set to 8 bits. These are also the default settings, so the hint was not necessarily needed.

![](https://user-images.githubusercontent.com/74334127/160300025-81b7ec95-da86-4057-9c78-16071a1c5808.jpg)
flag: `wsc{t0t4lly_w1ck3d_dud3}`
  
### Note
At least one team was able to do this without the use of photoshop, and just online tools. Will add this method to the writeup soon!


