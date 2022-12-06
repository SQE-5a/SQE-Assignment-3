Dolibarr is an OpenSource project built by the addition of modules (you only enable the features you need), on a WAMP, MAMP or LAMP server (Apache, Mysql, PHP for all Operating Systems).

# MicroServices
MicroServices are used when for one project,different separate independent projects having its all bundles of ui and backend ,are made called modules.You can use them in multiple projects.
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

# Extensibility

It is achieved mostly in websites by using previous code and just adding more sugar or more implementation to them.Its purpose is to modify or customize things which are already made.  
  
According to dolibarr documentation,The marketplace is open to everybody and serves as a central repository for hundreds of external add-ons which enhance Dolibarr for specific needs. You can also extend and enhance the features of your application by yourself, without any coding or development effort, by using the low-code Module Builder assistant. If the Module Builder does not offer all the customisation that you need, then you can take the route of custom development to achieve your business goals.  

Website Link of Extensibility information:
https://www.dolibarr.org/  



# Linters For Better Code Quality
Linters are basically guidelines set according to head developers team of the project to avoid small mistakes but these are not like the syntax error,  these are basically something else which you want your developers must do and if they don't do ,automatically should be fixed.

## According to dolibarr head team  
You can use git hooks to check the syntax of the file you commit and cancel the commit if something is wrong. You need phpcs command line tool for this (sudo apt-get -y install php-codesniffer). If you have phpcbf installed, you can also fix the files automatically.  
This is how to:  

Go to /dev/setup/git/hooks of your local repository, copy the file pre-commit into your .git/hooks folder of the local git repository and make it executable.  

Next, you need to edit pre-commit file in .git/hooks to modify the DIRPHPCS variable to set the path of your phpcs and phpcbf tool (you can keep it empty if tools are available into your PATH).  

Such hooks will work when using on command line but may also work when committing using your common IDE (it has been validated with Eclipse and VSC).  

Once installed, the hook will start on your next commit to re-format your code, so your code will always match the coding syntax rules. If everybody enable this   hook, everybody will use the same coding syntax rule, so it is highly recommended to enable it if you can. If something is wrong in the syntax, the commit will be   immediately canceled. If it can be fixed automatically, phpcbf will fix it so you just have to try the commit a second time to have it validated.  
## WebsiteLink of Reference
https://wiki.dolibarr.org/index.php?title=Environment_and_development_tools#Install_Pre-commit_git_hook  

Thats all.



