Dolibarr is an OpenSource project built by the addition of modules (you only enable the features you need), on a WAMP, MAMP or LAMP server (Apache, Mysql, PHP for all Operating Systems).

# MicroServices

Dolibarr project is using Microservices structure as they are using small modules with less coupling and independently which is simple to develop and modify.

![Enterprise-System-Integrated-with-a-Microservice-system](https://user-images.githubusercontent.com/113935723/204827023-09230158-d122-4e0f-a983-b30e8ad53cde.png)

## website Link of micro services information  
https://www.researchgate.net/figure/Overview-of-the-microservice-discovery-approach_fig2_336908349


# Modular folder structure

In Dolibarr project,modular code files are developed.
Modules of dolibarr presented on github account are arranged and organized in following way:

Customers, Prospects or Suppliers directory (CRM)  
Products and services catalog  
Bank accounts management  
Commercial actions management  
Orders management  
Commercial proposals management  
Contracts management  
Invoices management  
Project management (management of opportunities, organization of events, timesheets...)  
Payments management, online payment collect (via Paypal, Stripe, ...)  
Direct Debit and Credit Transfer management  
Stock, inventories and shipping management  
Manufacturing orders management (MRP)  
Following social and fiscal tax payments  
Double entre accounting, general and auxiliary accounting  
Agenda with ical,vcal export for third tools integration  
EDM/DMS (Electronic Document Management / Document Management System)  
Point of Sale for shops, bars or restaurants  
Foundations member management  
Expense reports  
Leave requests for employees  
Mass emailing  
Realize surveys  
Donations  
A lot of ready in-the-box Reporting  
PDF Generation of all managed objects (invoices, proposals, orders, shipments, stocks, ...)  
Import and export tools (CSV or Excel)  
LDAP connectivity.  
 
## Website Link of dolibarr modules information 
https://wiki.dolibarr.org/index.php?title=What_Dolibarr_Does#Main_modules_.2F_features  

## Github link of their modular structure files
https://github.com/Dolibarr/dolibarr/tree/develop/dev/initdata

# Reusability

It is achieved mostly in websites by making modules and using one module in another module like making header footer once and then using them in all other other pages modules.

Dolibarr have applied reusability concept by making modules and worked in the separate modules and use them when needed in another module which make the code easy and not copy pasting the code for every page.
Their development files are written in php language and In php files modules they have reused another modules by using require statement.





<img width="711" alt="reusability" src="https://user-images.githubusercontent.com/113935723/204856889-89656677-fa36-4c37-8b34-ec5ce25881d2.PNG">

