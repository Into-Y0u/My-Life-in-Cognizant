### Cakes and Order

![Cakes & Order](https://github.com/Into-Y0u/My-Life-in-Cognizant/blob/fa84948357164775484cd6049909d24498460e30/SQL%20Handson/CakeOrderingSystem%20(1).png)

# 1. Customer Details Based on Gmail Account : 
   Write a query to display the customer details who have a gmail account. Sort the result set based on the customer name in descending order.
   ```sh
   SELECT cust_id,cust_name,address,phone_no ,email_id FROM Customers WHERE Email_id LIKE '%@gmail.com' ORDER BY cust_name DESC;
   ```
# 2. Cake name with first letter 'C' : 
   Write a query to display the Cake name that starts with the letter 'C' and is priced more than 800 dollar. Sort the result set in descending order based on price.
   ```sh
   SELECT Cake_name FROM Cakes WHERE Cake_name LIKE 'C%' AND Price_Per_Kg > 800 ORDER BY Price_Per_Kg DESC ;
   ```
 
# 3. Order details based on date : 
  Write a query to display the order id, customer id, order date, delivery date of the orders where the order date and delivery date is not the same date. Sort the result based on the customer id in descending order..
  ```sh
  SELECT Order_id, Cust_id, Order_date, Delivery_date FROM Orders WHERE Order_date <> Delivery_date ORDER BY Cust_id DESC;
  ```
# 4. Customer Contact_Info : 
   Write a query to display the Customer id, customer name and phone number of the customer. If the phone number is not available, then display the email id. Give an alias as Contact_Info.  Sort the result set based on the customer name in ascending order.
   ```sh
   SELECT Cust_id, Cust_name,
  (
    CASE
      WHEN Phone_no IS NULL THEN Email_id
      ELSE Phone_no 
    END
  ) AS Contact_Info
   FROM
      Customers
   ORDER BY
      Cust_name;
   ```
