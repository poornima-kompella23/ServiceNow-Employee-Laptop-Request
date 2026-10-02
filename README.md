# ServiceNow Employee Laptop Request Application

## Project Overview

The **Employee Laptop Request Application** is a custom ServiceNow application developed to provide a centralized and controlled process for managing employee laptop requests.

The application allows employees to submit laptop requests, routes requests through manager approval, prevents duplicate requests within the same calendar year, and controls access using roles and ACLs.

---

## Business Objective

The main objective of this project is to replace manual laptop request processes such as email and verbal requests with a structured ServiceNow-based application.

### Business Goals

* Provide a single platform for employees to request laptops.
* Differentiate laptop usage based on business requirements.
* Prevent duplicate laptop requests within the same year.
* Provide visibility of requests to IT and management.
* Track request and approval status.
* Improve accountability through an approval workflow.
* Reduce dependency on manual request processes.

---

## Key Features

### Employee Laptop Request

Employees can submit laptop requests through the ServiceNow application using a Record Producer.

### Manager Approval

Submitted laptop requests are processed through an approval workflow so that the appropriate manager can review the request.

### Duplicate Request Validation

A Business Rule validates whether an employee has already submitted a laptop request during the current calendar year.

If a duplicate request is submitted, the system blocks the request.

### Role-Based Access

The application uses separate roles for employees and managers to control access to laptop request records.

* `it_employee`
* `it_manager`

### Access Control Lists

ACLs are configured to control what employees and managers can do with laptop request records.

### Request Status

The application tracks the request through statuses such as:

* Pending Approval
* Approved
* Rejected

The status is controlled by the application workflow rather than being freely editable by the requester.

### Notifications

Notifications are used to communicate important request and approval events.

---

## ServiceNow Components Used

| Component           | Purpose                                       |
| ------------------- | --------------------------------------------- |
| Custom Application  | Provides the overall application structure    |
| Laptop Request Form | Stores laptop request information             |
| Record Producer     | Provides the employee request form            |
| Flow Designer       | Automates the approval process                |
| Business Rule       | Prevents duplicate yearly requests            |
| Roles               | Controls user access                          |
| Groups              | Organizes employees and managers              |
| ACLs                | Controls record-level access                  |
| Notifications       | Communicates request events                   |
| Update Set          | Provides a portable application configuration |

---

## Application Workflow

```text
Employee
   ↓
Submit Laptop Request
   ↓
Duplicate Request Validation
   ↓
Manager Approval
   ↓
Approved / Rejected
   ↓
Request Status Updated
   ↓
IT / Management Tracking
```

---

## Security and Validation

The application was tested using different employee and manager scenarios.

### Employee Scenarios

* Employee can create a laptop request.
* Employee can modify permitted request information.
* Employee cannot submit another laptop request within the same calendar year when an existing request is present.

### Manager Scenarios

* Manager can view laptop request records.
* Manager access is controlled through the configured ACLs.
* Manager creation and modification are restricted according to the application security configuration.

---

## Project Structure

```text
ServiceNow-Employee-Laptop-Request/
│
├── README.md
│
├── Documentation/
│   └── Project Documentation
│
├── Screenshots/
│   └── ServiceNow Configuration & Testing Screenshots
│
└── Update-Set/
    └── Employee-Laptop-Request-Update-Set.xml
```

---

## Documentation

Detailed documentation covering the project requirements, configuration, implementation, and validation is available in the **Documentation** folder.

## Screenshots

ServiceNow configuration and testing screenshots are available in the **Screenshots** folder.

## Update Set

The ServiceNow application configuration export is available in the **Update-Set** folder.

The Update Set can be used to transfer the configured application components to another ServiceNow instance, subject to the appropriate instance and application configuration.

---

## Technologies Used

* ServiceNow
* Custom Applications
* Service Catalog
* Record Producers
* Flow Designer
* Business Rules
* ACLs
* Roles & Groups
* Approval Management
* Notifications
* Update Sets

---

## Project Outcome

The project provides a structured ServiceNow solution for managing employee laptop requests from submission through approval and tracking.

It demonstrates the use of **ServiceNow application development, workflow automation, business rules, role-based security, ACL configuration, approvals, notifications, and update set management**.

---

## Author

**Kompella Venkata Poornima Lakshmi**
