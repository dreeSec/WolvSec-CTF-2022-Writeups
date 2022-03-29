## Challenge Name: Where in the world?
Category: **OSINT**  
Difficulty: **Medium**  
Points: **486**  
Solves: **39**

Challenge Description: 
User Vividpineconepig claims on to live next to a street that's above some train tracks. Where are they? Maybe finding their social media could help. We’ll give you a flag for tracking them down. Give us this elevated STREETNAME preceding the St/Rd/Ave/Lane to prove it.

Format: wsc{STREETNAME}

### Approach

Vividpineconepig appears to be the name of some unique user. The description tells us we might want to find their social media account. Using tools like [Sherlock](https://github.com/sherlock-project/sherlock) we can find possible social media accounts of unique users. Once we try instagram, we find the following account and picture:

![4a990ad3409eb161cf8d7d681c8cb059](https://user-images.githubusercontent.com/74334127/160300607-3fa23b1d-c2e0-4b6a-a7f1-bfe2a1a642ac.png)
![bb194a9bc9ae06c57d4c5cdd9dd74af2](https://user-images.githubusercontent.com/74334127/160300608-b105ea2f-2ec8-4cc2-8fbd-c1cd84cfe07b.png)

One might initially think that we are going to need to brute force search the location, but we can actually narrow down this location using the two main clues in the picture. After doing research, one would find that the **Adopt a Highway sign** on the right is exclusive to the state on Montana. The other major clue is the **Mile 280** mile marker. Since we know the state is Montana, one might find this [Montana's DOT Mile Marker map](https://gis-mdt.opendata.arcgis.com/datasets/eaa5f283dd7f4a33bd30f8a392925e7f_0/explore?location=47.504619%2C-108.692992%2C7.94) to be useful. There are now very little locations you would have to check on programs such as google maps.

Once we find that the town is **Shelby, MT**, the next step is finding the streetname. From the picture, we might consider this elevated street over the traintracks to be the street the description is referring to.
![0b6851dca58be6533e87c436a5b62138](https://user-images.githubusercontent.com/74334127/160300873-44b07ed0-90d0-4625-980f-46f04c6f0760.png)

Looking on google maps, we can find the most updated street name (NOTE: If you check on google street view, it will give you an older name of the street, which is incorrect):

![5feec298809d5e60a58cc5be5e6f6af1](https://user-images.githubusercontent.com/74334127/160300930-e5316625-b4e5-4842-83f3-49c357f0e7ad.png)

Here, we can see the street is Oilfield Ave.

flag: `wsc{OILFIELD}`

Shoutout the [USA Geoguessr community](https://discord.gg/wx7CUMAxJQ)! would not have all adopt a highway signs memorized without them :)



