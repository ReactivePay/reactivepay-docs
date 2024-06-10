System Overview
===============

Abstract
--------

ReactivePay is a suite of products designed for financial institutions and the fintech industry.

All products created by ReactivePay are based on a Core system, which is essentially an immutable financial ledger.

With this project, we provide the development community with an open architecture and service design for all of our products.
Your team will always be part of our development community. Join us by following the link:

https://reactivepay.com/

Our development cycle follows the best practices prescribed by the PCI DSS, including:

- Regular ASV testing
- Penetration testing
- Annual QSA audit
- Central banks certifications
- Regular performance/regression testing

As for the development/deployment process, our team uses the following tech stack:

- RoR, Python
- GitLab CI/CD
- PostgreSQL, Mongo
- Redis
- Docker, Ansible

All tools and libraries included in the development process are regularly updated and audited.

ReactivePay Products and Components
-----------------------------------

- Digital banking solution
- Internet acquiring platform
- Core system (financial ledger)
- Crypto processing solution (merchant services)
- P2P payment platform
- E-money module (for EMI companies)

ReactivePay Web Applications
----------------------------

1. Checkout Payment Form:

- Desktop/Mobile friendly payment web-interface
- Alternative payment methods selection
- Checkout form customization

2. Digital Bank Application for End-Users

- Onboarding for personal and business accounts 
- Agile questionnaire for customer onboarding
- KYC/KYB/AML modules
- IBAN generation based on client's sort code
- Multicurrency accounts
- Internal ledger subsystem
- External/Internal transfers
- Currency exchange
- Client-based reports (Bank statements, commission reports, etc.)

3. Merchant Back Office

- Operation/Transaction historical data
- Settlements
- Dashboard with financial performance
- Dispute management
- Sub-merchants (websites)
- Role model (multiple user access)

4. E-money Web Application for End-Users

- Client onboarding through Authentication/KYC/KYB processes
- Internal money transfers
- Wallet/Account top-ups, withdrawals
- Currency exchange 

5. Flexy-Guard Admin Application (Payment Blacklists/Limits/Routing/Cascading)

- A rule-based engine for payment filtering
- Managing whitelists and blacklists
- A rule-based engine for payment routing
- A rule-based engine for payment traffic cascading

6. Flexy-Commission Admin Application (Fees/Rates/Commissions/Tariffs)

- A rule-based engine for making tariffs for any payment parameter
- Adding fixed fees for a payment
- Setting min/max amounts for commissions

7. Admin Web Application for System Managers

- Managing customers/accounts/merchants
- Browsing/Managing transaction/payment lists
- Setting up merchant connections with third-party payment providers
- Dispute processing
- Handling KYC/KYB for customers
- Financial operations on client accounts
- Handling settlements for merchants
- Reconciliation management

8. Business Intelligence and Reporting System

- Customizable reports/dashboards
- Charts/Graphs
- Alerts and notifications
- Data export (PDF, CSV, other formats)

Roles
-----

All modules support a role model for assigning certain rights to system users.
Each role is coded within the core, and more roles can be added by modifying the code within the Core.

- Business account (merchant) can use back-end and Public API
- System manager has access to: Admin app, BI system, Flexy-Commission and Flexy-Guard apps, Settings app
- Financial manager has access to: BI system, Admin app
- Risk manager has access to: Admin app, BI system, Flexy-Guard app, Settings app
- Technical support has access to: BI system

Roles also have separate access within every app.
For example: Manual refund function is available only for the financial manager.
Roles within the app can be assigned via the Admin app.

Customers can also create sub-users within the Merchant Back Office app and assign a particular role to each sub-user.

Architecture and Design
-----------------------

1. Tech Stack

- Sidekiq
- Docker
- Ansible
- Redis
- Ruby on Rails, Python
- PostgreSQL, MongoDB

2. Microservices

- Public API (business web service)
- Core service (core web service)
- Settings (system and account settings service)
- Flexy-Guard (payment filtering/routing/cascading rule engine)
- Flexy-Commission (managing tariffs/fees web service)
- Rates (web services for getting exchange rates from third parties)
- Static content storage

Security and Encryption
-----------------------

- Public API requests are optionally secured with RSA-SHA256
- Internal service communication is secured by DMZ network architecture and service-to-service authentication
- Sensitive data and customer private data are both encrypted in the database and can be stored in a dedicated location
  according to local regulatory requirements
- ReactivePay is a PCI DSS compliant solution
