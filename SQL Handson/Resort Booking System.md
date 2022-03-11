
# Resort Managment System

![Resort Booking](https://github.com/Into-Y0u/My-Life-in-Cognizant/blob/a8e0d46ae94e7e2747bcc11501e1b0cef1933563/SQL%20Handson/Resort.jpeg)

### 1. Create Booking Table: 
   Write a query to create a Booking table with constraints mentioned.
   ```sh
   CREATE TABLE booking (bookingid int,guestID int ,resortID int ,cabinID int ,fromdate Date ,todate Date ,adultCount int , childCount int ,petcount int , totalcharge int , 
PRIMARY KEY (bookingid)
);
   ```

### 2. Create town Table: 
   Write a query to create a Town table with constraints mentioned..
   ```sh
CREATE TABLE Town (
townID INT ,
townname varchar(30),
state  varchar(30) ,
longitude varchar(30),
latitude varchar(30),
summertemp int ,
wintertemp int ,
sealevel int ,
PRIMARY KEY (townID)
);
   ```
### 3. Alter Manager Table: 
   Refer to the given schema. Assume that the Manager table has been already created.
Write a query to change the data type of the field phone in Manager table to bigint(10) and rename the column as Phone_no.
   ```sh
alter table Manager 
change `phone` `Phone_no` bigint(10);
   ```
