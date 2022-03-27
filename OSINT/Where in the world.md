## Challenge Name: Where in the world?
Category: **OSINT**  
Difficulty: **Medium**  
Points: **476**  
Solves: **39**

Challenge Description: 
User Vividpineconepig claims on to live next to a street that's above some train tracks. Where are they? Maybe finding their social media could help. We’ll give you a flag for tracking them down. Give us this elevated STREETNAME preceding the St/Rd/Ave/Lane to prove it.

Format: wsc{STREETNAME}

### Approach

Vividpineconepig appears to be the name of some unique user. The description tells us we might want to find their social media account. Using tools like [Sherlock](https://github.com/sherlock-project/sherlock) we can find possible social media accounts of unique users. Once we try instagram, we find the following account and picture:

![4a990ad3409eb161cf8d7d681c8cb059](https://user-images.githubusercontent.com/74334127/160300607-3fa23b1d-c2e0-4b6a-a7f1-bfe2a1a642ac.png)
![bb194a9bc9ae06c57d4c5cdd9dd74af2](https://user-images.githubusercontent.com/74334127/160300608-b105ea2f-2ec8-4cc2-8fbd-c1cd84cfe07b.png)

  
If you run strings on the file, it will output hidden comments:
![22103aa00aedae679sss47c30b74cbd204e](https://user-images.githubusercontent.com/74334127/160298238-9769a267-43fc-4d3b-b447-b86baff1a6d6.png)

This is hinting that you will need to view this as a raw file in photoshop. This is also hinted in the description with RAW being capitalized. To convert it to a raw file, change the file extention from ".wav" to ".raw". Then, when trying to open the file in photoshop you are preseneted with the following options:

  ![](https://user-images.githubusercontent.com/74334127/160299927-56c70db3-7c64-43a4-8dfc-5995f85c8c30.png)
  
From the hint, we are given that the channels should be set to 1 and the depth should be set to 8 bits. These are also the default settings, so the hint was not necessarily needed.

![](https://user-images.githubusercontent.com/74334127/160300025-81b7ec95-da86-4057-9c78-16071a1c5808.jpg)
flag: `wsc{t0t4lly_w1ck3d_dud3}`
  
### Note
At least one team was able to do this without the use of photoshop, and just online tools. Will add this method to the writeup soon!


