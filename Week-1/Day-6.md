#  User role controlled by request parameter

## Objective:
- Understand how cookies and other request parameters can be used to exploit broken access control.

## Logs
- The lab stated that the site uses a cookie that identifies the admin status
- task was to access the admin panel using the given credentials
- When  i opened the lab and logged in, there was no "Admin pannel"
- So i right clicked and used the inspector tool
- Under the "Aplication" section, I found the cookies
- There was a cookie named **admin** with a value **false** 
- I changed the value to true, hit enter, and refreshed the web page
- An admin panel link appeared on the navigation giving me access to admin functions(Vertical privilege escslstion)

## Conclusion
I've learned how basic things like cookies if not handled properly can be used to exploit broken access control. 