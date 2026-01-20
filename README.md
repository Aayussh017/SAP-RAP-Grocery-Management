# SAP-RAP-Grocery-Management

📦 SAP RAP – Grocery Management Application

Repository: SAP-RAP-Grocery-Management
Technology: SAP ABAP RAP (RESTful ABAP Programming Model)
Platform: SAP BTP – ABAP Environment (Trial)
UI: Fiori Elements (OData V4)

📌 Project Overview

This project demonstrates the implementation of a transactional RAP business object for managing grocery items.
It follows SAP-recommended clean RAP architecture using CDS view entities, managed behavior, and Fiori Elements.

The application allows users to:

View grocery items in a Fiori List Report

Navigate to an Object Page

Manage grocery data lifecycle using RAP behavior

Automatically calculate expired status via RAP determinations

🏗️ RAP Architecture Used
1️⃣ Database Layer

Transparent table: ZGRC_DATA

Stores grocery master data

UUID-based primary key

2️⃣ CDS Interface View

Z_I_GROCERY_PRJ

Root CDS view entity

Directly mapped to database table

Used as the transactional interface

3️⃣ CDS Consumption View

Z_C_GROCERY_PRJ

Projection on interface view

Exposed to UI and OData

Annotated for Fiori Elements

4️⃣ Behavior Definition (Managed)

Managed implementation

Supports:

Create

Update

Delete

Includes:

Determination to calculate expired flag

5️⃣ Behavior Implementation

ABAP class implementing business logic

Handles:

Automatic expiration calculation

Action handling logic

6️⃣ Service Definition & Binding

OData V4 service

Published and consumed via Fiori Elements Preview

🔁 Business Logic
🔹 Expired Flag Calculation

Implemented using RAP determination

Triggered on:

Create

Update

Logic:

Compares expiration date with system date

Sets expired status accordingly

Note: Determinations are lifecycle-based and run only during RAP-managed modifications.

🖥️ Fiori UI Features

List Report displaying grocery items

Object Page for item details

Navigation via UUID

Standard SAP Fiori Elements layout

No custom UI coding (annotation-driven UI)
