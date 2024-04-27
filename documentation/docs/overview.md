---
sidebar_position: 1
---

# Introduction to Evoton System

## Overview

This document provides a comprehensive overview of the Evoton System, a Node.js project structured around a microservices architecture. This system is designed to handle various aspects of property management, including separate interfaces for property managers, tenants, landlords, and asset management.

## Project Structure

The project is divided into several main components: server (backend), clients (frontends), and common (shared code and resources). Below is the detailed folder structure:

```
evoton-system/
│
├── server/                  # Backend source
│   ├── src/
│   │   ├── api/            # API layer (controllers, routes)
│   │   ├── config/         # Configuration files
│   │   ├── services/       # Business logic
│   │   ├── models/         # Database models
│   │   ├── middleware/     # Custom middleware
│   │   └── utils/          # Utility functions
│   ├── tests/               # Automated tests
│   └── package.json        # Node package file for backend
│
├── clients/                 # Frontend applications
│   ├── property-manager/    # Separate frontend for the property manager
│   ├── tenant/              # Separate frontend for tenants
│   ├── landlord/            # Separate frontend for landlords
│   └── assets/              # Separate frontend for asset management
│
└── common/                  # Shared resources and utilities
    ├── dto/                 # Data transfer objects
    ├── interfaces/          # TypeScript interfaces, if used
    └── constants/           # Shared constants
```

## Module Description

### API Layer (`api/`)

- `property/`:
  - **propertyController.js**: Handles requests and responses for property management.
  - **propertyRoutes.js**: Routes for property management operations.
- Similar structure and purpose apply for `tenant/`, `landlord/`, and `asset/`.

### Services (`services/`)

- **propertyService.js**: Business logic for managing properties.
- Other services such as `tenantService.js`, `landlordService.js`, and `assetService.js` are organized similarly.

### Models (`models/`)

- **propertyModel.js**: Database schema for properties.
- Similar models for `tenantModel.js`, `landlordModel.js`.

## Naming Conventions

- Filenames and variables use **lowerCamelCase**.
- Names are descriptive and indicate the file's purpose, like `propertyManagement`, `tenantManagement`.

## Configuration and Utilities

- **Configurations** (in `server/src/config`): Includes database connections and other settings.
- **Utilities** (in `server/src/utils`): Common utilities like logging and error handling.

## Scalability and Maintenance

The structure supports scalability by allowing new modules to be added seamlessly and common functionalities to be shared.

## Additional Resources

Links to coding standards, tools, and external resources used within the project.

## Conclusion

This document is intended to guide developers and stakeholders in understanding and contributing to the Evoton System. For further information or to contribute to this documentation, please contact the project team.
