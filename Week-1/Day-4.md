# Mass Assignment & Parameter Pollution

## Objective
- Test how the backend processes hidden parameters. Try injecting parameters like is_admin=true into account creation or profile update fields.

## Logs
- I opened the lab on my burp browser
- Thr instructions stated that I needed to explor a mass assignment vulnurability to try and purchase a product for free.
- I went ahead and logged in using the provided credentials
- I added the product to my cart and proceeded to checkout
- The feedback was **"Insufficient funds"**
- I then fount the **POST** request in the http history on burp suite `POST /api/checkout`
- I sent this request to the repeater to analyse it
- I observed that it contained the parameters: 
```json
{"chosen_products":[
    {
        "product_id":"1",
        "quantity":1
    }
]
}
```
- I noticed the **GET** request that came after and I also sent it to the repeater for analysis
- This time, there was an additional parameter:
```json
{
    "chosen_discount":{
        "percentage":0
    },
    "chosen_products":[
        {
            "product_id":"1",
            "name":"Lightweight \"l33t\" Leather Jacket",
            "quantity":1,"item_price":133700
        }
    ]
}
```
- There is a parameeter for changing the discount on the product. Lets see if we can exploit that
- I went back to the post request and added the discount parameter setting the percentage to 100:
```json
{
    "chosen_discount":{
        "percentage":100
    },
    "chosen_products":[
        {
            "product_id":"1",
            "quantity":1
        }
    ]
}
```
- I sent the request and it worked. I was able to purchase the product for free

## Conclusion
I was able to understand mass assignmet and parametre pollution with the notes given on port swigger. WIth my understanding, i was able to esploit a vulnurability unassisted and successfully purchase a product for free.
This has improved my understanding of how to read and translate requests to try and find vulnurabilities.
 