# Notes
- stores customer info in database
- hard code vendor info on pega and inside html file.. do not store them in the database.
- customer expense report is going to be generated and stored in the database.
- Robot should shop from two vendors (so uipath automation will have to come in at some point after databse and website is created).
- you can print out of stock message for items not found

# Goals
- create a database of customers:
    - Name
    - Item
    - 

# update
- tables:
    - client: pk(clientId), Name, Email
    - ShoppingList: pk(itemId).. combo of client product and qty, fk(clientId), ProductName, Quantity
    - Order: pk(orderId), fk(clientId), orderDate, Total
    - Shopping Expense: pk(lineItemId), Fk(OrderId), FK(Item), Subtotal, Price

# pega notes:
- items that don't have the issue with qty beign selected:
<!--     - Chai, Chartreuse verte, Sasquatch Ale, Steeleye Stout and Laughing Lumberjack Lager.
 -->


- to update stuff:
<!-- UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1; -->
- add: last name, street address, zip code, area code and phone number.
<!-- download azure data studio or querry everything from azure -->

# my website notes implementation in uipath
- have limited activites compared from pega
- create a datatable to mimic and store info into the orderlist table
- if orderList does not work, then use shoppingExpense as another orderList table (eventhough this is technically wrong)
- have execute query outside the foreach loop
- use variables to store:
    - should all exist in foreach loop so that it stores the price, qty and total of each client's shopping items shopping trip
    - price.. initial = 0
    - qty
    - total = price * qty
- 