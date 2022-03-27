## Challenge Name: <Noise>
Category: **Forensics**  
Difficulty: **Medium**
Points: **498**  
Solves: **17**

Challenge Description: 
My buddy sent me this totally RAW clip of them playing guitar. Doesn’t sound quite right to me, something might be off. Also don’t listen with headphones at the end!

### Approach
This challenge was based off of [Joshua Casper's](https://youtu.be/tU8WbB9vhDg) stegonagraphy idea!

While listening to the audio file, you can hear the audio has gotten corrupted towards the end of the recording. 
  
If you run strings on the file, it will output hidden comments 
![22103aa00aedae679sss47c30b74cbd204e](https://user-images.githubusercontent.com/74334127/160298238-9769a267-43fc-4d3b-b447-b86baff1a6d6.png)



![Anything Solution](https://user-images.githubusercontent.com/74334127/160296838-ba774a01-ed11-4285-aa7f-6692a9eabd58.png)

flag: `wsc{vigenere_not_bad}`
