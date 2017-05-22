# File Carving
In this lab you'll learn about File Carving. File Carving goes one step beyond reading raw binary data. In File Carving, you are editing and manipulating binary data as well. You are basically cutting and pasting one file inside of another in order to hide it.   

Begin with the following image:   
![carvingex.jpg](carvingex.jpg)   

It looks like an ordinary picture, but it is hiding a secret message. *Right click* on the `carvingex.jpg` file, and choose *Save Image* to download the picture. Now, start HxD and open `carvingex.jpg` so you can read through the raw binary data.
```
00008e20: 3fff d950 4b03 0414 0000 0008 0088 6c0c  ?..PK.........l.
00008e30: 3f18 f066 802d 0000 0032 0000 000a 001c  ?..f.-...2......
00008e40: 0061 6e73 7765 722e 7478 7455 5409 0003  .answer.txtUT...
00008e50: 9f72 454e 126d 454e 7578 0b00 0104 8813  .rEN.mENux......
00008e60: 0000 0488 1300 000b c9c8 2c56 00a2 acd2  ..........,V....
00008e70: e212 85c4 3c85 d48a c4dc 829c 546b 8592  ....<.......Tk..
00008e80: 8cd4 a254 904c 5e3e 50bc b83c b548 0124  ...T.L^>P..<.H.$
```
.zip files always start with the hex code `50 4B 03 04` which looks like `PK..` in the ASCII field. Immediately preceding the PK is the hex code `FF D9`, which is the end of file marker for a jpeg file. Somebody has hidden a zip file at the end of the data for the picture! 
Use HxD to delete all the data in front of the `PK..` Save the file as `answers.zip`, and then Extract All to discover what was in the hidden file. Write the contents of the hidden file and show your instructor the hidden message.

Use the same technique on the following image and write the answer down and show it to your instructor.  
![carving.jpg](carving.jpg)   

We can hide other files in pictures as well. The following picture has zip file of another picture. *Right click* on `PuppyCarving.jpg` and repeat the process. Write what the thing is in the hidden picture and check your answer with your instructor.   
![PuppyCarving.jpg](PuppyCarving.jpg)

*this assignment was adapted from http://dirtbags.net/ctf/tutorial/carving.html*
