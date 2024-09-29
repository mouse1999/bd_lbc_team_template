# oneSquadDesign Document


## *Food Delivery Application* Design

## 1. Problem Statement

The goal of this project is to develop a simple food delivery application that allows customers to browse restaurants,
view menus, place orders, and receive order confirmations. The application should connect customers to their preferred restaurants,
facilitating a seamless ordering experience.



## 2. Top Questions to Resolve in Review

1. Should there be different roles for users and restaurant owners?
   
2. How should cancellations be handled from both the user and restaurant sides? Is it better for only users to cancel orders,
 while restaurant owners focus solely on updating the status of the cuisine or food item? 
 
3. Should there be filters for cuisine, or price range? 

4. Should the app use push notifications for real-time updates?

## 3. Use Cases

U1. As a user, I want to create an account so that I can place orders and manage my profile.

U2. As a user, I want to update my account information so that my profile details are current.

U3. As a user, I want to delete my account if I no longer wish to use the service.

U4. As a restaurant owner, I want to create an account so that I can add menus and receive orders.

U5. As a user, I want to view a list of all available restaurants so that I can choose where to order from.

U6. As a user, I want to view the menu of a specific restaurant so that I can decide what to order.

U7. As a restaurant owner, I want to add a new menu so that customers can see and order from my menu.

U8. As a restaurant owner, I want to delete all menus in case the menu is outdated or no longer available.

U9. As a user, I want to search for food by name or price so I can easily find the dishes I am interested in.

U10. As a user, I want to view all menus across different restaurants to explore options.

U11. As a user, I want to place an order from a restaurant.

U12. As a user, I want to view a list of all my orders so that I can keep track of my order history.

U13. As a user, I want to view the details of a specific order using an order ID.

U14. As a user, I want to cancel an order if I change my mind.

U15. As a restaurant owner, I want to view the list of orders placed at my restaurant so that I can process them.

## 4. Project Scope

### 4.1. In Scope

*Which parts of the problem defined in Sections 1 and 3 will you solve with this
design?*

* Allow users to register and log in to the application.

* Enable users to browse a list of available restaurants.

* Provide users with menus from selected restaurants.

* Allow users to place orders from their chosen restaurant.

* Send order confirmation notifications to users.

### 4.2. Out of Scope


* Handling payments is not part of this version.

* The app won't provide real-time delivery tracking.

* No system for customer reviews or ratings for restaurants or food items.

* No notifications for order status updates.

* No advanced search capabilities, such as filtering restaurants by ratings, distance, or other criteria.

* The app will not support promo codes, discounts, or loyalty rewards.

* No authentication will be required for restaurants to add or update their menu items after creating an account.


# 5. Proposed Architecture Overview

This initial iteration will provide the minimum lovable product (MLP) for a food delivery application, focusing
on key functionalities like account creation for users and restaurants, menu management, order placement, and retrieval of orders.
We will use API Gateway and AWS Lambda to create multiple endpoints that handle user and restaurant registration, menu management, and 
order placement, ensuring the basic requirements of the app are satisfied.
*include names of API later.*

We will store users, restaurants, menus, orders, and food items in separate DynamoDB tables. Each entity will have its dedicated 
table, while relationships between entities (such as restaurant menus and user orders) will be handled efficiently using partition 
and sort keys in DynamoDB.

The food delivery service will also provide a web interface for users to browse restaurants, view menus, and place orders, as 
well as for restaurant owners to manage their menus.

# 6. API

## 6.1. Public Models

*Define the data models your service will expose in its responses via your
*`-Model`* package. These will be equivalent to the *`PlaylistModel`* and
*`SongModel`* from the Unit 3 project.*

## 6.2. *First Endpoint*

*Describe the behavior of the first endpoint you will build into your service
API. This should include what data it requires, what data it returns, and how it
will handle any known failure cases. You should also include a sequence diagram
showing how a user interaction goes from user to website to service to database,
and back. This first endpoint can serve as a template for subsequent endpoints.
(If there is a significant difference on a subsequent endpoint, review that with
your team before building it!)*

*(You should have a separate section for each of the endpoints you are expecting
to build...)*

## 6.3 *Second Endpoint*

*(repeat, but you can use shorthand here, indicating what is different, likely
primarily the data in/out and error conditions. If the sequence diagram is
nearly identical, you can say in a few words how it is the same/different from
the first endpoint)*

# 7. Tables

*Define the DynamoDB tables you will need for the data your service will use. It
may be helpful to first think of what objects your service will need, then
translate that to a table structure, like with the *`Playlist` POJO* versus the
`playlists` table in the Unit 3 project.*

# 8. Pages

*Include mock-ups of the web pages you expect to build. These can be as
sophisticated as mockups/wireframes using drawing software, or as simple as
hand-drawn pictures that represent the key customer-facing components of the
pages. It should be clear what the interactions will be on the page, especially
where customers enter and submit data. You may want to accompany the mockups
with some description of behaviors of the page (e.g. “When customer submits the
submit-dog-photo button, the customer is sent to the doggie detail page”)*
