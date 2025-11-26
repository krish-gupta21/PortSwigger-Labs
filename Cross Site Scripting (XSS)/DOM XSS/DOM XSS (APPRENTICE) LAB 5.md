Lab: DOM XSS in jQuery selector sink using a hashchange event

Description: This lab contains a DOM-based cross-site scripting vulnerability on the home page. 
             It uses jQuery's $() selector function to auto-scroll to a given post, whose title is passed via the location.hash property.
             To solve the lab, deliver an exploit to the victim that calls the print() function in their browser.

1. The lab is about a jQuery sink using a hashchange event . The home page doesn't have not much functionality just a bunch of posts and and "Go to exploit server" Button.

   <img width="1883" height="890" alt="image" src="https://github.com/user-attachments/assets/71ad51d3-392b-4764-81ad-5f45904060d0" />

2. In the DEV tools it showed that the home page contains a script in which the script listens for hashchange events , what it means that whatever we put after the "HASH" in the "URL", the script decodes it and
   inserts it as a selector in jQuery funtion. And in this code it scrolls to the specified post which is mentioned after the "HASH" in the "URL".

   <img width="651" height="200" alt="image" src="https://github.com/user-attachments/assets/f295694a-43f1-4022-b4f5-570809001910" />

3. So after examining the code and found post names in "h2" tags and after entering one of the post name in the "URL" after the "HASH" the page auto scrolls to the specified post.
   Which shows that whatever we put after the "HASH" the code inserts into the jquery function.

   <img width="1897" height="954" alt="image" src="https://github.com/user-attachments/assets/e597d9c3-cee6-40e0-9b36-3d6a4840ba50" />

4. So now after understanding how the script works. I went to the exploit server page, where we can craft a payload , test it and send it to the victim.

   <img width="1739" height="880" alt="image" src="https://github.com/user-attachments/assets/b534443b-783f-4f16-94c5-5cf645ffbf26" />

5. In the Body section created a payload with the "iframe" tag in which iframe source as the lab id with an appended hash and in the onload parameter inserted a payload that gets appended to the "HASH"
   as the onload gets triggered . And then the script takes the new hash and creates a new query with it and then executes the "onerror=print()" (as mentioned in description to use print() to complete the lab
   but alert() also works). After pressing the "View Exploit" the payload got executed a print popup showed up.

   <img width="1872" height="901" alt="image" src="https://github.com/user-attachments/assets/71aa4959-f598-492b-bca8-e75e3e74ebc7" />

   <img width="1881" height="948" alt="image" src="https://github.com/user-attachments/assets/8b31cbe4-68c1-41a6-a5ec-f08449e2932f" />

6. Now it's time to send the paylaod to the victim (my lab) and after clicking "Deliver exploit to vicitim" we can see that the lab gets solved.

   <img width="1901" height="891" alt="image" src="https://github.com/user-attachments/assets/cc8155b0-d6af-4c07-84bc-93905feba34e" />

7. Inorder to test it manually we can directly put the payload in the "URL" after the "HASH" and we can see a popup.

   <img width="1891" height="944" alt="image" src="https://github.com/user-attachments/assets/43d5edf7-7295-4830-9c73-afad2ce6415c" />


