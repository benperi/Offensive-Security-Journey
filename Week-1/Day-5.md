# Bypassing Flawed Access Controls

## Objecctives
- Evade shallow authorization blocks that rely strictly on user-tamperable state indicators,
custom client headers (e.g., X-Forwarded-For), or front-end element hiding.

## Logs
- The lab stated the the website had front end protection, but the back end supports the `X-Original-Url` framwork which has vulnurabilities
- My task was to access the admin panel on the lab
- I opened the lab and when I clicked on the admin panel I was met with an, "Access denied message"
- So, on burp, I opened the **GET** request for the admin panel from the click
- I tried adding an `X-Original-Url: /admin` header.
- I was still met with "Access denied"
- After some thinking and looking around, I figured that the reques coming from the front end was for the admin panel, and since there was protection there, it was blocked from there and changing the backend wont do anything.
- If I use a request that wont get blocked from the front end, maybe it"ll work.
- So I used the **GET** request for the home page and put the `X-Original-Url: /admin` there and sent it.
- I didn't get any error messages this time so that was good.
- I refreshed my browser and this time, when I clicked the admin panel, the was no error, and I was granted admin controls.

## Conclusion
I now understand that even if your frontend is secured, If your backend isn't, broken acces control can be exploited.
Also, I understood that there are some frameworks that are known to have vulnurabilities so I should always be up to date.