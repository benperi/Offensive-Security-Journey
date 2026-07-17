# HTTP And Paameter Mapping

## Objectives
- Get faminliar with BurpSuit UI.
- learn how to link browser to burp or use the burp browser.
- Lern to use the intercept and repeater.

## Logs

I watched an installation guide to help me install BurpSuit properly. Aftee that, I watched a quick beginer guide to familiarise myself with the UI.
I proceeded to follow a youtube guide on how to use Proxy to monitor my traffic using BurpSuit.
I proceeded to run a quick intercept test, then fowarded it. I learnt what the repeater was used for.

## Challenges and workarounds
+ After setting my browser's proxy ro be intercepted by burp, I started getting an error message indicating that the connection wasn't secure
    - I trid watching youtube but I couldn't find any video to solve the problem
    - I described the problem to gemini ai and it explained that i was getting the warning because the browser did not trust brp suite to intercept traffic and that i need to install a cirtificate tha tells the browser that it's safe.
    - I followed the instructions and instslled the cirtificates and i was able to move on.
+ When using burp, I fond that pages on my browser took forever to load(Infinte loading)
    - I again described the problem to AI and it suggested a couple of possible causes
    - Turns out when Intercept is "on" in burp, it stops the request from beig sent until it is manually fowarded
    - So i turned of intercept, since i wasn't actively usinng it.



## Conclusion
I Sucessfully installed burp suite, learned how to link it to my browser. I unexpectedly learned something new about how cirtificates work while trying to debog a problem. I familiarised myself with the interface and got ready to actually start using burp the next day



