### Cakes and Order

![Cakes & Order]()

1. Write a query to display the customer details who have a gmail account. Sort the result set based on the customer name in descending order.
   ```sh
   SELECT cust_id,cust_name,address,phone_no ,email_id FROM Customers WHERE Email_id LIKE '%@gmail.com' ORDER BY cust_name DESC;
   ```
3. Install NPM packages
   ```sh
   npm install
   ```
4. Enter your API in `config.js`
   ```js
   const API_KEY = 'ENTER YOUR API';
   ```
