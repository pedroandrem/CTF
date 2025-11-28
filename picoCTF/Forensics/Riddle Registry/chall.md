## Challenge Name: <Riddle Registry>
Category: <Forensics>
Difficulty: <Easy>

Challenge Description: 
<Hi, intrepid investigator! 📄🔍 You have stumbled upon a peculiar PDF filled with what seems like nothing more than garbled nonsense. But beware! Not everything is as it appears. Amidst the chaos lies a hidden treasure—an elusive flag waiting to be uncovered.
Find the PDF file in files, named Hidden Confidential Document and uncover the flag within the metadata.
>

Files:
* [Hidden Confidential Document]()

### Approach

**1. <Question_1_description>?/flag1**
First thing i did was checking pdf's metadata with exiftool. With that i obtained this:

![img](<image_link>)

**2 <Question_2_description>?/flag2**
I noticed that the Author was something strange, so i checked and it seems its written in Base64. 
I used another tool to decode from Base64. Finding this: picoCTF{puzzl3d_m3tadata_f0und!_c999e2a4}
![img](<image_link>)


### Reflections
<reflections ...>
  

---
[Back to home](<link>)