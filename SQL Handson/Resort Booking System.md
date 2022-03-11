
# Resort Managment System

![Resort Booking](https://github.com/Into-Y0u/My-Life-in-Cognizant/blob/fa84948357164775484cd6049909d24498460e30/SQL%20Handson/CakeOrderingSystem%20(1).png)

### 1. Customer Details Based on Gmail Account : 
   Write a query to display the customer details who have a gmail account. Sort the result set based on the customer name in descending order.
   ```sh
   SELECT cust_id,cust_name,address,phone_no ,email_id FROM Customers WHERE Email_id LIKE '%@gmail.com' ORDER BY cust_name DESC;
   ```
