# 📺 Netflix-Subscriber-Analysis

📌 Project Overview

This project provides an Entity-Relationship Diagram (ERD) for a Netflix-like streaming platform, along with a set of SQL queries designed to analyze user data, content engagement, subscriptions, and payment behaviors. The database models various entities such as customers, profiles, content, devices, payment methods, and plans.

📊 Entity-Relationship Diagram (ERD)

The ERD visually represents the relationships between the different entities in the database. The key entities include:

* Customers: User data such as name, birth date, gender, email, country, and language preferences.
* Profiles: Sub-accounts under a customer, including profile name, parental controls, and account type (adult/child).
* Plans: Subscription plans with details like video quality, number of supported devices, and pricing.
* Content: Shows and movies available for streaming, categorized by genre and category.
* Viewing History: Tracks what content each profile has watched, along with timestamps and runtime.
* Devices: Tracks which devices users watch content on.
* Payment Methods: Stores user payment details, including billing address and card information.
* Payment History: Logs payments made by users.

📝 Database Schema & Columns

1️⃣ Customers Table
Cust_ID (INT, PK) – Unique ID for each customer
Fname (VARCHAR) – First name
Lname (VARCHAR) – Last name
BDate (DATE) – Birth date
Gender (VARCHAR) – Gender of the customer
Email (VARCHAR) – Email address
Country (VARCHAR) – Country of residence
LanguagePreferred (VARCHAR) – Preferred language

2️⃣ Profiles Table
ProfileID (INT, PK) – Unique ID for each profile
ProfileName (VARCHAR) – Profile name
MaxParentalRating (INT) – Maximum parental rating
NoOfChildren (INT) – Number of child profiles
AdultAcc (BOOLEAN) – Indicates if it's an adult account
ChildAcc (BOOLEAN) – Indicates if it's a child account
Cust_ID (INT, FK) – Customer who owns the profile

3️⃣ Plans Table
PlanID (INT, PK) – Unique ID for the plan
PlanName (VARCHAR) – Name of the subscription plan
MonthlyPrice (DECIMAL) – Monthly cost of the plan
VideoQuality (VARCHAR) – Video quality (SD, HD, UHD)
NumofProfiles (INT) – Maximum number of profiles allowed
NumofSupportDevforViewing (INT) – Number of supported viewing devices
NumofSupportDevforDownload (INT) – Number of supported download devices
AdSupport (BOOLEAN) – Whether ads are included
ContentAccess (TEXT) – Type of content accessible

4️⃣ Content Table
ContentID (INT, PK) – Unique ID for content
TitleName (VARCHAR) – Title of the content
Genre (VARCHAR) – Genre category
Category (VARCHAR) – Movie or Series
UnlimitedAccess (BOOLEAN) – Whether it is available for unlimited streaming

5️⃣ Viewing History Table
ProfileID (INT, FK) – Profile watching the content
ContentID (INT, FK) – Content being watched
LastWatchedDate (DATE) – Last watched date
Runtime (TIME) – Total runtime watched

6️⃣ Devices Table
DeviceID (INT, PK) – Unique ID for the device
DeviceType (VARCHAR) – Type of device (Mobile, TV, Laptop, etc.)

7️⃣ Payment Methods Table
PaymentID (INT, PK) – Unique ID for payment method
CardID (INT) – Unique card identifier
CardNumber (VARCHAR) – Credit/Debit card number
CVV (INT) – Security code
ExpirationDate (DATE) – Expiry date of the card
BillingAddress (TEXT) – Address associated with the card

8️⃣ Payment History Table
PaymentID (INT, FK) – Payment method used
PaymentAmount (DECIMAL) – Amount paid
PaymentDate (DATE) – Date of transaction

![image](https://github.com/user-attachments/assets/e05f3ca3-55e5-43a8-bf11-69c3b0710fa5)

🔍 SQL Query Questions

The database is designed to answer key business questions such as:

* User Engagement

1. How many profiles are created per customer?
2. What are the most watched content titles?
3. How many hours of content has each profile watched?

* Subscription Analytics

1. What is the distribution of customers per subscription plan?
2. How many users are using ad-supported plans vs ad-free?
3. What is the average revenue per customer?

* Device Insights

1. hat are the most used device types for streaming?
2. How many devices are linked per profile?
   
* Content Performance

1. Which genre is the most popular?
2. What is the average runtime of watched content?
3. How frequently do users return to a particular title?

* Payment & Revenue Analysis

1. What is the monthly revenue from subscriptions?
2. What is the churn rate (customers who canceled their subscriptions)?
3. How often do customers update their payment methods?
