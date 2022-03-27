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
  
If you run strings on the file, it will output hidden comments:
![22103aa00aedae679sss47c30b74cbd204e](https://user-images.githubusercontent.com/74334127/160298238-9769a267-43fc-4d3b-b447-b86baff1a6d6.png)

This is hinting that you will need to view this as a raw file in photoshop. This is also hinted in the description with RAW being capitalized. To convert it to a raw file, change the file extention from ".wav" to ".raw". Then, when trying to open the file in photoshop you are preseneted with the following options:

  ![](https://user-images.githubusercontent.com/74334127/160299927-56c70db3-7c64-43a4-8dfc-5995f85c8c30.png)
  
From the hint, we are given that the channels should be set to 1 and the depth should be set to 8 bits. These are also the default settings, so the hint was not necessarily needed.

![](https://user-images.githubusercontent.com/74334127/160300025-81b7ec95-da86-4057-9c78-16071a1c5808.jpg)
flag: `wsc{t0t4lly_w1ck3d_dud3}`
  
### Note
At 


