##Demand
###User group
+ General User
+ Admin  

###Log in
+ General User: input username&pwd, if these are in a correct format the insert userinfo to database and show register successfully.
+ Admin : Fix username&pwd
###Goods management
Admin can add/delete/change goods info which contents:
1. Name
2. Princess
3. Amount available(when ==0,disable the "Buy" button)
4. Description
5. Picture  

General user can buy goods
1. Goods can be bought only when (amount >0)&&(user's money is more than price)
2. User can buy a item once.(No cart)
3. Change the amount available when goods be bought successfully.  
###User info  
features:
+ User name
+ Order (Order ID/Time/Goods Name/Amount/Total price)
+ Balance
+ Address  

##Database  
###User table
1. username
2. ID
3. pwd
4. Balance

###Goods table
1. Name
2. ID
3. Description
4. price
5. Amount
6. Picture

###Order table
1. Order ID
2. Time
3. Good ID
4. Purchase quantity
5. Total price
6. Consumer ID

###Shipping Address table
1. Address ID
2. Country
3. Province
4. City
5. Full Address
6. Postal code
7. Tel
8. Consumer ID

## User Flow
1. Access main page without login, just two button in this page, one for login and one for registering.
2. Register:After fill in the input group (name/pwd/repeat pwd), redirect to "show" page,userinfo -> DB.
3. Show page, show some items' info(only pic&name), click any item to the detail page.
4. Detail page: show full info of goods with buy button, fill in amount you want to buy and click this but to payment page.
5. Payment page : show payment info, input the pwd, if (amount >0)&&(user's money is more than price)&&(shipping address is not empty), succeed to buy it. Otherwise alter ErrorInfo and return.
6. In the top-right of navigation bar show username. After click it, redirect to UserInfo page.
7. UserInfo page: show user info , recharge button and Shippint-Address-Set button.
8. Recharge page:
input the money you want to recharge and pwd, click confirm, done. Change DB->userinfotable->balance.
9. Set shipping address.(To be simple, each user has only one address).
![Picture](https://github.com/geekinglcq/Buy2Die/blob/master/UI%20layout.png)
