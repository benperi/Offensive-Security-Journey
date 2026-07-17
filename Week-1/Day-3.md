# Identifying ANd Exploring Basic IDORs

## Objective: 
- Locate direct object reference vulnerabilities in URI paths or body keys (e.g., swappingtracking variables from 1001 to 1002) to extract unauthorized records.

## Logs
- I logged into my port swigger account and went to the lab that exploits IDOR.
- The instrucctions spoke about a vulnurability in the chat system.
- I opened the lab, and navigated to the "chat" section, I sent some messages and got replies from the chatbot.
- There was a "View Transcript" button there so I clicked it. A text file called `2.txt` was downloaded to my laptop, I opened it and it was just a log of the conversation I had with the chatbot. 
- Then it got me thinking, if the file was downloaded as "2.txt", there must be a "1.txt". 
- So i went to my BurpSuite, under the proxy section i selected "http history" to see all the requests that have been made. 
- I located the **GET** request for the transcript and I sent it to the repeater for more examining.
- I analysed the request and niticed that it was `GET /download-transcript/2.txt HTTP/2` **Interesting** 
- So i tried editing it to `GET /download-transcript/1.txt HTTP/2` then i sent it.
- In the responce section, I noticed it was another chat history between another user and the chatbot, The chatot helped the user who firgit his password and the password was written in plain text `Ok so my password is 4rxk3808hgon5wchccaf.` 
- I was able to gain access to this user's account using this password and their username.

## Conclusion 
I was able to successfully exploit an IDOR. This helped me to further understand the concept of broken access control.
My understanding of the burpsuite interface was improved, and, I developed new understanding for **GET** and **POST** requests.