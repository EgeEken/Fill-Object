# Fill-Object
Fills any closed objects found within the given image

# V1
Version 1 of this program uses a system that checks in N directions for every pixel to see if there is a border (represented by a black pixel in white space, the code could be altered to use different colors instead) in all of those directions. If there is, it detects that the pixel is surrounded, and assumes that it is inside an object.

![explanation 8D](https://user-images.githubusercontent.com/96302110/181605407-8e1217a5-a341-46a2-b711-a4e62d111758.png)

<details><summary>Results (click here to open)</summary>
<p>

## 8D check
![Result2](https://user-images.githubusercontent.com/96302110/181616177-5a199aaa-7d34-4299-856e-b6d21a19b5d1.png)

## 32D check
![Result1](https://user-images.githubusercontent.com/96302110/181615417-a6839f6c-9e9d-4bfe-95a4-3a86d95c4572.png)

## 48D check
![Result3](https://user-images.githubusercontent.com/96302110/181619835-385958c4-d4f3-4c04-b9e8-642c6a3baab4.png)

</p>
</details>

<details><summary>Possible problems</summary>
<p>
  
<details><summary>1-) Not enough directions being checked</summary>
<p>
  
## A problem with using a small amount of directions to check is the risk that gaps in the surrounding area can be missed, a mostly viable solution is to increase the direction count until a satisfactory result is reached

![explanation benefit of 16D](https://user-images.githubusercontent.com/96302110/181606796-9f725a7a-3acd-49a3-b69c-7b93322cc5cc.png)
</p>
</details>
  
<details><summary>2-) Borders too thin</summary>
<p>
  
## However, as the direction count is increased, another problem shows up, The checks start jumping over the borders if they are thin enough

![explanation of problem with more directions in checks on a pixel basis](https://user-images.githubusercontent.com/96302110/181607564-9f734a23-7cb7-4dca-9b06-b1cd0e979852.png)

## Due to the nature of digital images, using pixels, it is impossible to get certain angles without jumping over a few coordinates that may be necessary to understand whether or not the pixel is actually surrounded

![explanation of jumping over pixels to check precise angles on a pixel basis](https://user-images.githubusercontent.com/96302110/181608078-6db5e62f-bcbe-42a1-9dd1-d4c078abb115.png)
</p>
</details>
  
<details><summary>3-) Problem with directional checking as a concept</summary>
<p>
  
## But even if there was somehow a way to fix the two previous problems, there is a fundamental issue with the concept of directional checking to understand if a given pixel is truly surrounded by the borders of an object. Even if we had the infinite computing power to check for infinite angles, and an infinitely large canvas with infinitely wide borders for every object to get rid of any phasing problems that may occur, a simple spiral or two boxes inside one another with holes on opposite sides would still be enough to defeat this algorithm. 

![explanation of problem with v1 as a concept](https://user-images.githubusercontent.com/96302110/181608757-f34bfab7-bc23-4959-9e9f-890db67f1e50.png)
</p>
</details> 
</p>
</details>

### The only way to solve these problems is by using something like a maze solving algorithm, which is what the upcoming V2 will be doing, stay tuned!

# V2

Coming soon (maybe not that soon actually)
