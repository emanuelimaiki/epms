---
sidebar_position: 3
---

# Models

This documentation provides detailed information on each database model used within the Evoton Property Management System. Each model description includes field definitions and their purposes to facilitate understanding and development.

## Tenant Model

The `Tenant` model represents individuals renting properties through EPMS.

- **Fields**:
  - `name`: String, required - The tenant's full name.
  - `email`: String, required, unique - The tenant's email address.
  - `phone`: String, required - The tenant's phone number.
  - `leaseDetails`: [ObjectId] - References to the tenant's current and past lease agreements.

## Landlord Model

The `Landlord` model stores information about property owners who utilize EPMS to manage their properties.

- **Fields**:
  - `name`: String, required - The landlord's full name.
  - `contactInfo`: String, required - Contact details, typically a phone number or email.
  - `propertiesOwned`: [ObjectId] - References to properties owned by the landlord.

## Property Model

The `Property` model contains details about rental properties managed within EPMS.

- **Fields**:
  - `address`: String, required - Physical address of the property.
  - `landlordId`: ObjectId, required, ref: 'Landlord' - Reference to the landlord who owns the property.
  - `status`: String, required - Current rental status (e.g., "available", "occupied").

## PaymentAccount Model

The `PaymentAccount` model is used to manage financial transactions and balances related to tenants and landlords.

- **Fields**:
  - `ownerId`: ObjectId, required, ref: 'Tenant' or 'Landlord' - The account owner.
  - `balance`: Number - Current account balance.
  - `transactions`: [type: ObjectId, ref: 'Transaction'] - List of all transactions.

## HistoricalOccupancy Model

The `HistoricalOccupancy` model tracks the rental history of properties.

- **Fields**:
  - `propertyId`: ObjectId, required, ref: 'Property' - The property in question.
  - `tenantId`: ObjectId, ref: 'Tenant' - The tenant occupying the property.
  - `startDate`: Date - Start date of tenancy.
  - `endDate`: Date - End date of tenancy, if applicable.

## FieldManager Model

The `FieldManager` model stores data about employees who oversee physical property management tasks.

- **Fields**:
  - `name`: String, required - The field manager's name.
  - `region`: String, required - Geographical region of responsibility.
  - `contact`: String, required - Contact information for the field manager.

## PrePayment Model

The `PrePayment` model manages advance payments made by tenants.

- **Fields**:
  - `tenantId`: ObjectId, required, ref: 'Tenant' - The tenant making the prepayment.
  - `amount`: Number, required - Amount of prepayment.
  - `date`: Date, required - Date the prepayment was made.

## Further Documentation

Continue detailing other models such as `Floorplan`, `TenantHistories`, `Zone`, etc., following the format outlined above.
