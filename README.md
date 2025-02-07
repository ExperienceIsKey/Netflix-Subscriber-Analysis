# 📺 Netflix-Subscriber-Analysis

📌 Project Overview
This project provides an Entity-Relationship Diagram (ERD) for a Netflix-like streaming platform, along with a set of SQL queries designed to analyze user data, content engagement, subscriptions, and payment behaviors. The database models various entities such as customers, profiles, content, devices, payment methods, and plans.

📊 Entity-Relationship Diagram (ERD)
The ERD visually represents the relationships between the different entities in the database. The key entities include:

Customers: User data such as name, birth date, gender, email, country, and language preferences.
Profiles: Sub-accounts under a customer, including profile name, parental controls, and account type (adult/child).
Plans: Subscription plans with details like video quality, number of supported devices, and pricing.
Content: Shows and movies available for streaming, categorized by genre and category.
Viewing History: Tracks what content each profile has watched, along with timestamps and runtime.
Devices: Tracks which devices users watch content on.
Payment Methods: Stores user payment details, including billing address and card information.
Payment History: Logs payments made by users.
📝 Database Schema & Columns
1. Customers Table
Column Name	Data Type	Description
Cust_ID	INT (PK)	Unique ID for each customer
Fname	VARCHAR	First name
Lname	VARCHAR	Last name
BDate	DATE	Birth date
Gender	VARCHAR	Gender of the customer
Email	VARCHAR	Email address
Country	VARCHAR	Country of residence
LanguagePreferred	VARCHAR	Preferred language
2. Profiles Table
Column Name	Data Type	Description
ProfileID	INT (PK)	Unique ID for each profile
ProfileName	VARCHAR	Profile name
MaxParentalRating	INT	Maximum parental rating
NoOfChildren	INT	Number of child profiles
AdultAcc	BOOLEAN	Indicates if it's an adult account
ChildAcc	BOOLEAN	Indicates if it's a child account
Cust_ID	INT (FK)	Customer who owns the profile
3. Plans Table
Column Name	Data Type	Description
PlanID	INT (PK)	Unique ID for the plan
PlanName	VARCHAR	Name of the subscription plan
MonthlyPrice	DECIMAL	Monthly cost of the plan
VideoQuality	VARCHAR	Video quality (SD, HD, UHD)
NumofProfiles	INT	Maximum number of profiles allowed
NumofSupportDevforViewing	INT	Number of supported viewing devices
NumofSupportDevforDownload	INT	Number of supported download devices
AdSupport	BOOLEAN	Whether ads are included
ContentAccess	TEXT	Type of content accessible
4. Content Table
Column Name	Data Type	Description
ContentID	INT (PK)	Unique ID for content
TitleName	VARCHAR	Title of the content
Genre	VARCHAR	Genre category
Category	VARCHAR	Movie or Series
UnlimitedAccess	BOOLEAN	Whether it is available for unlimited streaming
5. Viewing History Table
Column Name	Data Type	Description
ProfileID	INT (FK)	Profile watching the content
ContentID	INT (FK)	Content being watched
LastWatchedDate	DATE	Last watched date
Runtime	TIME	Total runtime watched
6. Devices Table
Column Name	Data Type	Description
DeviceID	INT (PK)	Unique ID for the device
DeviceType	VARCHAR	Type of device (Mobile, TV, Laptop, etc.)
7. Payment Methods Table
Column Name	Data Type	Description
PaymentID	INT (PK)	Unique ID for payment method
CardID	INT	Unique card identifier
CardNumber	VARCHAR	Credit/Debit card number
CVV	INT	Security code
ExpirationDate	DATE	Expiry date of the card
Billing Address	TEXT	Address associated with the card
8. Payment History Table
Column Name	Data Type	Description
PaymentID	INT (FK)	Payment method used
PaymentAmount	DECIMAL	Amount paid
PaymentDate	DATE	Date of transaction
🔍 SQL Query Questions
The database is designed to answer key business questions such as:

User Engagement

How many profiles are created per customer?
What are the most watched content titles?
How many hours of content has each profile watched?
Subscription Analytics

What is the distribution of customers per subscription plan?
How many users are using ad-supported plans vs ad-free?
What is the average revenue per customer?
Device Insights

What are the most used device types for streaming?
How many devices are linked per profile?
Content Performance

Which genre is the most popular?
What is the average runtime of watched content?
How frequently do users return to a particular title?
Payment & Revenue Analysis

What is the monthly revenue from subscriptions?
What is the churn rate (customers who canceled their subscriptions)?
How often do customers update their payment methods?
