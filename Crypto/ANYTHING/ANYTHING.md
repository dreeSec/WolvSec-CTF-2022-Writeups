## Challenge Name: ANYTHING
Category: **Crypto**  
Difficulty: **Easy**  
Points: **100**  
Solves: **241**

Challenge Description: 
This could be encrypted with ANYTHING!
`wfa{oporteec_gvb_ogd}`

### Approach

1.The flag seems to be encrypted by some 1:1 cipher, since there are still 3 letters before the flag. The challenge name and description imply that the word “Anything” might be useful to help decrypt this msg. Since the first letter is not encrypted, and the first letter of anything is an A, one might be able to deduce that this is a vigenere cipher. Putting it through a vigenere cipher on [dcode](https://www.dcode.fr/vigenere-cipher) yields the following results: 

![Anything Solution](https://user-images.githubusercontent.com/74334127/160296838-ba774a01-ed11-4285-aa7f-6692a9eabd58.png)

flag: `wsc{vigenere_not_bad}`
