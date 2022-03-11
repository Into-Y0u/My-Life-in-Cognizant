
# Resort Managment System

![Resort Booking](https://github.com/Into-Y0u/My-Life-in-Cognizant/blob/a8e0d46ae94e7e2747bcc11501e1b0cef1933563/SQL%20Handson/Resort.jpeg)

### 1. Create Booking Table: 
   Write a query to create a Booking table with constraints mentioned.
   ```sh
   CREATE TABLE booking (bookingid int PRIMARY KEY  ,guestID int ,resortID int ,cabinID int ,fromdate Date ,todate Date ,adultCount int , childCount int ,petcount int , totalcharge int 
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
### 4. Insert Records into Manager Table: 
   ```sh
INSERT into Manager VALUES (3,'SWATHI' , '1 ARYA ROAD' , NULL , 9798611111);
INSERT into Manager VALUES (10,'KARAN' , '16 HSR LAYOUT' , 'BANGALORE' , NULL);
INSERT into Manager VALUES (11,'ARJUN' , '17 VIVEKANDA STREET' , 'BANGALORE' , 9798676549);
   ```
### 5. Insert Records into Guest Table: 
   ```sh
INSERT into Guest VALUES (3456, 'ANUP SAXENA' , '116,STRELING ROAD, OOTY' , 'INDIA' , 'anup@hotmail.com' , 919090909090);
INSERT INTO Guest VALUES (3457, 'RAKSHA KAPOOR' , '52,VELALLAR STREET,CHENNAI' , 'INDIA' , 'raksha@gmail.com',917867867834);
INSERT into Guest VALUES (3458,'PADMAVATHI MANE' , '14/2 WESTGATE RD,HYDRABAD' , 'INDIA','padma@yahoo.com' , 911234565432);
   ```
### 6. Update Revised Cabincost: 
Write a query to update the revised cabin cost of Cabin id 1 and 3 which have been increased by $1000 from the current rate.
   ```sh
update
  CabinCost
SET rate = rate -  10000
WHERE
  cabinID = 1  ;
update
  CabinCost
SET rate = rate -  10000
WHERE
  cabinID = 3;
   ```
### 7. Update Booking price: 
Write a query to  update the total charge and pet count of the guest who stayed in Resort Id 1004 where pet count is increased by 2 and should pay an additional amount of 1500  from the current total charge of the booking..
   ```sh
UPDATE
  Booking
SET
  petcount = petcount + 2,
  totalcharge = totalcharge + 1500
WHERE
  resortID = 1004;
  ```
