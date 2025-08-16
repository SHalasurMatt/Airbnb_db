

```markdown
🏡 Airbnb Database Schema & Analytics

This repository provides a **full-featured simulation of an Airbnb-style property rental database**, designed for **SQL Server**.  
It includes a **highly normalized schema**, **robust business logic** (procedures and functions), and a **rich set of example queries** for analytical insight.  

Use this project for learning **relational data design**, **ETL workflows**, and **complex SQL business analytics**.

---

 📦 Files Included

- **Airbnb_ERD.drawio.jpg**  
  Entity-Relationship Diagram – visual overview of all tables, relationships, and data flow.  

  ![Airbnb ERD Schema](Airbnb_ERD.drawio.jpg)

- **Airbnb_Code.sql**  
  Main SQL script containing:
  - DDL statements to create tables, constraints, and foreign keys  
  - Initial lookup/data insertion  
  - Wrapper procedures to automate population (ETL simulation)  
  - Scalar functions for business logic (age, ratings, payment, taxes)  
  - Example analytics and reporting queries  

---

 🏗️ Schema Highlights

| Table              | Key Columns / Features         | Description                                                   |
|--------------------|--------------------------------|---------------------------------------------------------------|
| **Customer**       | Name, Age, City, Gender, Type  | Registered guests, demographic & rating info                  |
| **Host**           | Name, City, Gender, DOB        | Property owners                                               |
| **Listing**        | Address, City, Host, Price     | Rental property details                                       |
| **Amenity**        | Name, Type, Description        | Individual amenities (e.g. BBQ, Patio, Kitchen, etc.)         |
| **Booking**        | Dates, Listing, Customer       | Records of reservations                                       |
| **Payment**        | Type, Amounts, Booking         | Split payments (deposit, pending), tax, final calculation     |
| **Review & Rating**| Booking, Text, Score           | Post-booking feedback & ratings                               |
| **Reference Tables**| City, State, Gender, CustomerType, AmenityType, PaymentType, Rating | Lookup for classification and integrity |

- Amenities are linked to Listings via a **junction table**: `ListingAmenity` (with quantity).  
- Reviews are tied to Bookings and Ratings.  
- Strong use of **foreign keys** ensures referential integrity.  

---

 🛡️ Business Rules

- Customers must be **≥ 13 years old**; Hosts **≥ 21 years old**.  
- Listing prices are capped at **$1,000**.  
- Ratings must be in the range **1–5 (Lousy → Excellent)**.  
- Maximum booking duration: **10 days**.  
- Payments are split into **deposit, pending, tax, and final amounts**.  
- Referential integrity enforced across all relationships.  

---

 ⚙️ ETL / Population Procedures

Wrapper procedures streamline data loading via raw staging tables:  

- `Wrapper_InsertCustomer`  
- `Wrapper_InsertHost_Listing`  
- `Wrapper_InsertBooking`  
- `Wrapper_InsertReview`  
- `Wrapper_InsertListingAmenity`  
- `Wrapper_InsertPayment`  

These automate **bulk population** and **transform logic** for demo data.  

---

 📊 Example Analytics Queries

The project includes several pre-built queries for analysis:

- Most **popular city by state** for bookings  
- **Seasonal revenue** ranking per year  
- % of **Senior customers** booking stays > 7 days  
- **Top loyal customers** by total spend  
- Cities with hosts offering **BBQ AND Patio amenities**  
- **Top listings by rating** category  
- States with highest **Youth winter bookings**  
- **Seasonal & yearly booking volumes**  
- **Price vs. Customer Type** segmentation  

All queries are provided as **commented blocks** in the SQL script.  

---

 🖼️ Entity-Relationship Diagram

![ERD](Airbnb_ERD.drawio.jpg)

---

 🚀 Quick Start

1. **Create your SQL Server database** → `Airbnb_db`  
2. **Run** `Airbnb_Code.sql` → builds schema, rules, reference data, and loads demo data  
3. **Open** `Airbnb_ERD.drawio.jpg` → explore table relationships  
4. **Run example queries** → learn SQL analytics & insights  

