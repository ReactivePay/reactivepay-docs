System overview
===============

Abstract
--------

ReactivePay is a number of product designated for financail institutions and fintech industry.

All products created by ReactivePay are based on a Core system which basically is an immutable financial ledger. 

With this project we provide the development comunity with open architecure and service design for all of our products.
Your team will be always the part of our developement comunity, join us by following the link:

https://reactivepay.com/

Our development cycle follows the best practices prescribed by the PCI DSS, including:

- Regular ASV testing
- Penetration testing
- Annual QSA audit
- Central banks certifications
- Regular performance/regression testing

As for the development/deployment process our team is using the following tech stack:

- RoR, Python
- Gitlab CI/CD
- PostgreSQL, Mongo
- Redis
- Docker, Ansible

All tools and libs included in the development process are regulary updated and audited.


ReactivePay products and components
-----------------------------------

- Digital banking solution
- Internet acquiring platform
- Core system  (financial ledger)
- Crypto processing solution (merchant services)
- P2P payment platform
- Emoney module (for EMI companies)

ReactivePay Web Applications
----------------------------

1) Checkout payment form:

- Desktop/Mobile friendly payment web-interface
- Alternative payment methods selection
- Checkout form customization

2) Digital bank application for end-users

- Onboarding for personal and business accounts 
- Agile questionaire for cusomter onboarding
- KYC/KYB/AML modules
- IBAN generation based on client's sort code
- Multicurrency accounts
- Internal ledger sub system
- External/Internal transfers
- Currency exchange
- Client based reports (Bank statements, commission reports, etc)  

3) Merhcant back office

- Operation/Transaction historical data
- Settlements
- Dashboard with financial performance
- Dispute management
- Sub-merchants (web-sites)
- Role model (multiple user's access)

4) Emoney web application for end-users

- Client onboarding through Authentication/KYC/KYB processes
- Internal money transfers
- Wallet/Account top-up(s), withdrawals
- Currency exchange 

5) Flexy-guard admin application (Payment black lists/limits/routing/cascading)

- A rule based engine for payment filtering
- Managing white lists and  black lists
- A rule based enging for payment routing
- A rule based enging for payment traffic cascading

6) Flexy-commission admin application (Fees/Rates/Commissions/Tariffs)

- A rule based engine for making tariffs for any payment parameter
- Adding fixed fees for a payment
- Setting min/max amount for commissions

6) Admin web application for the system managers

- Managing customers/accounts/merchants
- Browsing/Managing transaction/payment lists
- Setting up merchant connection with 3d party payment providers
- Dispute processing
- Handling KYC/KYB for the customers
- Financial operations on the client accounts
- Handling settlements for merchants
- Reconciliation management

7) Business intellegence and reporting system

- Customizable reports/dashboards
- Charts/Graphs
- Alerts and notifications
- Data export (PDF, CSV, other formats)

Roles
-----

All modules support a role model for assign certain rights to the system users.
Each role is coded withing the core and more roles could be added by modiying the code withing Core.

- Busness account (merchant), can use back-end and Public API
- System manager has access to: Admin app, BI system, Flexy-commission and Flexy-guard apps, Settings app.
- Financial manager has access to: BI system, Admin app
- Risk manager has access to: Admin app, BI system, Flexy-guard app, Settings app
- Technical support has access to: BI system

Also roles have separated access within every app.
For example: Manual refund function is available only for financial manager.
Roles withing the app could be assigned via Admin app.

Also customers can create subusers within Merhcant back office app and assign a particular role for each subuser

Architecture and design
-----------------------

1) Tech stack

- Sidekiq
- Docker
- Ansible
- Redis
- Ruby on Rails, Python
- PostgreSQL, MongoDB

2) Micro services

- Public API (business web service)
- Core service (core web serivce)
- Settings (system and account settings service)
- Flexy-guard (payment filtering/routing/cascading rule engine)
- Flexy-commission (managing tariffs/fees web serivce)
- Rates (wweb services for getting exchange rates from 3d parties)
- Static content storage

Security and encryption
-----------------------

- Public API requests are optionally secured with RSA-SHA256
- Internal service communication secured by DMZ network architecture and service-to-service authentication
- Sensitive data and customer private data both are encrypted in database and could be stored on dedicated location
  according to local regulatory requirements
- ReactivePay is PCI DSS compatible solution
