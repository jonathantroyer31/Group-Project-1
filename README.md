    
# Group Project Chick-fil-a


## Group Repos
Jonathan - https://github.com/jonathantroyer31/Group-Project-1

Carol - 

Lena - 

Lily - 

Valerie - 




## Problem Description

Chick-fil-A is a fast-food restaurant chain that specializes in chicken sandwiches, nuggets, biscuits, and other chicken-based dishes. Chick-fil-A allows franchisees to own and operate a Chick-fil-A restaurant which is depicted by a restaurant location. Owners can franchise one restaurant or multiple and each restaurant has their own operations and employees. The locations have the same menu which comes down from Chick-fil-A headquarters. As any fast food operation, Chick-fil-A has a menu filled with items that customers can order from. Additionally, Chick-fil-A has ingredients which are used in making the food the restaurant sells. Chick-fil-A has employees who have shifts as well because the employees help run operations through cooking, taking orders, cleaning, doing dishes, etc. Chick-fil-A also has customers who have loyalty accounts so they can obtain rewards, among other things. Overall, Chick-fil-A's business operation prioritizes high-quality food made with fresh ingredients and exceptional customer service. Corporate also emphasizes the importance of franchise partnerships and fostering the mission and vision of the company. 
## Data Model

![image](https://user-images.githubusercontent.com/128402127/229163316-4191a7b8-0901-48f2-b128-c67e94afadb5.png)


The owner of the Athens Chick-fil-A franchise location has three branches: Downtown, Beechwood, and Atlanta Highway. These locations have many employees. An employee can manage many people but an employee can only be managed by one person so a recursive one to many relationship exists. Employees have many shifts and shifts can have many employees. The associative entity ShiftDetails that is present between Employees and Shifts has additional attributes like clock in date and time and clock out date and time. This is an identifying many-to-many relationship. 

Employees can work on many orders. Customers place many orders. We have a one to one relationship between customer and loyalty as a customer can have one loyalty account and vice versa. Orders and Menu Items have a many to many relationship where an order can have multiple menu items and a menu item can be in multiple orders. The associative entity between the two is Order Details which has additional attributes like item quantity and order time. Menu items and ingredients have a many to many relationship as menu items have many ingredients and an ingredient can be in multiple menu items. The ensuing associative entity is menuItemDetails.

Each location has a unique identification number, location name, address, and phone number. 
Each employee has a unique identification number, first name, last name, phone number, address, email, and position. Each shift has a unique identification number, shift start time, and shift end time. Each customer has a unique identification number, first name, last name, phone number, address, and email. The loyalty table has a unique identification number, loyalty status, loyalty points, and date joined. Each order has an order number, type, and status. Each menu item has a unique identification number, a name, price, description, and an attribute for if it is in stock. Each ingredient has a unique identification number, a name, price, and quantity. 

## Augmented Data Model
After looking at our data model, we came to the conclusion that we could augment it by adding a Promotions table. Athens CFA locations have many promotions. For instance, the Beechwood location does Bingo night. In addition, specific CFAs send out rewards to their customers. In order to represent this, we created the entity Promotion. The primary key is promID and the other attributes are promoType (for promotion type), promoDate (for promotion date), promoCost (for promotion cost). We created a many to many relationship between Location and Promotion since many locations have promotions and promotions can be present in many locations. The associative entity between Location and Promotion is PromotionDetails. Promotion Details has an identifying relationship between Promotion and Location. Apart from these changes, the model remains the same.

## Data Dictionary
The data dictionary file shows the columns for each table which includes the name of the column, the descption, the type of data, the size of the data, the format of the data, and if the data is a primary or foreign key. 
![image](https://user-images.githubusercontent.com/128402127/229163829-b647b3cb-d050-419a-b43d-bb07b0a8c885.png)
![image](https://user-images.githubusercontent.com/128402127/229163951-f1227234-ba99-4638-9be1-8654cd98291c.png)
![image](https://user-images.githubusercontent.com/128402127/229164173-a1183058-977d-42be-a0a8-9fe3cde86671.png)
![image](https://user-images.githubusercontent.com/128402127/229165148-e93e7349-4ff2-4beb-ab71-8b877444c104.png)
![image](https://user-images.githubusercontent.com/128402127/229165416-cbf5968b-ad73-46a3-a2d9-d74ebf4470c2.png)
![image](https://user-images.githubusercontent.com/128402127/229165598-b97e5965-a0fb-411a-ae83-fdc149bcfc51.png)
![image](https://user-images.githubusercontent.com/128402127/229165680-2b70cf78-4ef2-49f5-ab56-a6c60fe7fbd1.png)

## Queries
#1
 
Description: What customers have a Signature loyalty status?

Justification: This query will allow the store owners and managers to acquire a list of their most loyal and frequent customers. The Signature status and loyalty program in general allow CFA to create an ongoing relationship with their frequent customers. This list can specifically be used to send out surprise rewards to customers with Signature status only which is something that CFA currently does.

#2
 
Description: How many Red status loyalty members do we have?

Justification: This query will create a promotional list where the CFA team can send a promotional email to these customers who have loyalty accounts and are already frequent customers that are one step down from the “Signature” loyalty status which is the highest level. Managers will want to see how many customers they have that are still frequent and that can hopefully be bumped up to the highest status.

#3
 
Description: How many employees have taken more than 3 orders?
Justification: This will give the manager insight into whether or not their employees are doing their job by keeping track of the orders they took.

#4
 
Description: How many employees worked on April 17th, 2022?

Justification: If there were to be an incident on a specific day, the manager could look at who was working that day to ask the employees that worked that day for more information. 

#5
 
Description: Which employees have not worked in 5 months?

Justification: A manager would be interested in obtaining a list of employees who have not worked in five months to see if these employees should still be on the payroll. If employees have not worked in five months, they may no longer want to work and the manager needs to know this to make staffing decisions and for budget considerations.

#6
 
Description: What percentage of customers have ordered a kids meal?

Justification: A manager would be interested in obtaining the percentage of customers who have ordered a kids meal because this statistic will impact menu planning, inventory management, and cost management. For menu planning, if a lot of customers order kids meals, the owner can get feedback about what menu items are popular and what changes can be made.

#7
 
Description: Which menu items have orders in which the quantity of item ordered is greater than the average quantity for that item?

Justification: A manager would be interested in obtaining the amount of orders that have a larger quantity than the average amount in order so that they are able to forecast sales and maintain inventory management. By understanding which menu items are ordered in larger quantities, they can adjust inventory levels and fulfill all orders while balancing the cost of ordering inventory. 

#8
 
Description: What is average order size and the amount of employees working on orders during lunch hour (12 - 2)?

Justification: A manager would be interested in the average order size and number of employees that worked during the lunch rush because results would influence how shifts are staffed. If the average indicates that there are many large orders during a specific time, a manager would schedule more employees to reflect the busy nature of the restaurant and vice versa. 

#9
 
Description: How many products of each type are left in inventory at the beechwood location?

Justification: The managers of the store must know how much inventory they currently have. This is extremely important to know because it determines when to order more products and how much to purchase. Chick-fil-a is known for its reliability so it is vital that everything is in stock and delivered on time. 

#10
 
Description: Which location has sold the most amount of Mac and Cheese?

Justification: The manager must know which location has sold the most of a certain item because he or she will be able to see which location has the highest profitability. This is important because if one location is struggling at selling the item, this may show that they are preparing the item wrong, not marketing correctly, or having some other kinds of issues. By having the data to see which location is excelling with this item, the others can learn from it and overall profitability can increase. 


## Query Matrix

The query matrix provides a description of the complexity of each query which includes multiple table joins, subqueries, correlated subqueries, REGEXP, built-in function, calculated fields, where, not exists, group by, having, and order by. 

    
