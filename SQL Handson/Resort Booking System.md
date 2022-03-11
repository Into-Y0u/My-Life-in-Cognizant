
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
### 8. Review with Guest Details: 
Write a query to display the guest name, resort id and date of review of all the guests who are from 'CALIFORNIA'. Sort the result set based on the guest name in ascending order.
   ```sh
select g.name , r.resortID , r.dateofreview  from review AS r natural JOIN Guest
AS g where g.country = 'CALIFORNIA' OR g.country = 'California'   order by g.name ;
  ```
### 9. Display Manager Details: 
Write a query to display the manager's name of all the resorts as given in the sample output. Give the alias name as MANAGER_DETAILS. Sort the result set based on the resortname in ascending order.
SAMPLE DATA
MANAGER_DETAILS
name is the manager of resortname
SAMPLE OUTPUT:
MANAGER_DETAILS
JESSICA MARK is the manager of GRAND MOUNT
  ```sh
select CONCAT(name ," is the manager of " , ResortName) AS Manager_Details from Manager natural join Resort  order by ResortName;
  ```
### 10. Display booking Details based on date: 
Write a query to display the booking Id, guest name, resort name of the guest who all stayed in the month of April 2019. Sort the result based on descending order of booking id.
  ```sh
select dISTINCT b.bookingID , g.name , r.resortName from Booking AS b inner join Guest AS g 
ON g.guestId = b.guestId inner JOIN Resort AS r ON r.resortID  = b.resortID 
where (Month (b.fromdate )) = 4 and (Year (b.fromdate )) = 2019 order BY bookingID DESC ; 
  ```
### 11. Number of Places in each Town: 
Write a query to display the town name and number of places in each town. Give an alias name as 'NUMBER_OF_PLACES'. Sort the resort based on the town name in descending order.
  ```sh
select t.townname , count(p.pointID) AS NUMBER_OF_PLACES from Town as t natural join
PointofInterest as p group by t.townID order by t.townname desc ; 
  ```
### 12. Number of Guest in each Resort: 
Write a query to display the resort id, resort name, number of guests booked in each resort and star rating. Give an alias name to number of guests booked as 'NO_OF_GUEST'. Sort the result set based on the resort id in the descending order.
  ```sh
select  b.resortId , r.resortName , count(b.resortId) AS NO_OF_GUEST , r.starRating from Resort as r natural join Booking as b group by b.resortid 
order BY r.resortid desc ; 
  ```
### 13. Guest details based on their stay: 
Write a query to display the unique guest id, guest name, phone number and address of all the guest who stayed in the resort for more than 5 days. Sort the result based on descending order of guest name.
  ```sh
select distinct g.guestid , g.name , g.phone , g.address from Guest g natural join 
Booking b where  b.todate- b.fromdate  >= 5 order by g.name desc ;
  ```
### 14. Guest Details based on date: 
Write a query to display the name and address of all the guest who all stayed in 20-December- 2019. Sort the result based on the guest id in descending order .
  ```sh
select  g.name , g.address from Guest g inner join Booking b on g.guestid = b.guestid where '2019-12-20'= b.fromdate 
order by b.guestid desc ;
  ```
### 15. Guest details who make more than 1 booking: 
Write a query to display the guest id,name,phone number and country of all the guests who have made more than 1 booking. Sort the result based on ascending order of guest name.
  ```sh
select  g.guestID , g.name , g.phone , g.country 
from Guest g natural join Booking b 
group by g.guestID
having count(b.bookingid)   > 1
order by g.name ;
  ```
