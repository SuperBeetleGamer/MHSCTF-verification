# 1 Chal 2 Categories

OK it's one chall, 2 categories (reversing and pain/guessing)

First the reversing part. We modify the script that was given to reverse the process:

```python
from PIL import Image

def glorp(n):
    g = list(format(n, "08b"))
    for i in range(len(g)):
        t = g[i]
        g[i] = g[(i * 332 + 6) % 8]
        g[(i * 332 + 6) % 8] = t
    return int(''.join(g), 2)

#lookup = [glorp(i) for i in range(256)]
lookup = {glorp(i):i for i in range(256)}

img = Image.open("flag.png")
pix = img.load()

for i in range(img.size[0]):
    for j in range(img.size[1]):
        pix[i, j] = (lookup[pix[i, j][0]], lookup[pix[i, j][1]], lookup[pix[i, j][2]])

img.save("encoded.png")
```
This gets us an image, but the flag seems to be overlayed on itself in a weird way.

We fiddle around with which columns show up, modifying our script:

```python
for i in range(img.size[0]):
    for j in range(img.size[1]):
        if i%4==0:
            pix[i, j] = (lookup[pix[i, j][0]], lookup[pix[i, j][1]], lookup[pix[i, j][2]])
```

By changing which value mod 4 is selected, we can pull out different "layers" of the image.

Two of the ones that stand out:

![](https://cdn.discordapp.com/attachments/943687475627442246/944384972133908540/unknown.png)
![](https://cdn.discordapp.com/attachments/943687475627442246/944385346710433812/unknown.png)

The first part of the flag (`flag{two_`) is obvious, and we get the second part by taking every other character from the second picture.

We have our flag: `flag{tw0_st3p5_t0_v1c70ry}`
