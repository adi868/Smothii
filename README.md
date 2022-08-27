# Smöthii

## About Smöthii
Smöthii is an encompassing interactive interface for a fresh smoothie vending machine. The Smöthii application allows a customer to select and purchase a Smöthii from a list of official recipes or personally create a custom Smöthii from the available ingredients. Once the customer has selected a Smöthii to purchase, a vending interface directs the customer throughout the full purchase and Smöthii production.

## Installation
The Smöthii app relies on Node.js to provide the web server, and MySQL to store vending machine data (Smöthiis, ingredients, recipes, Smöthii purchases and ingredient restocks).  There are a number of Node.js packages used to extend functionality listed below.

1. [Download](https://nodejs.org/en/download/) and install Node.js
2. [Download](https://dev.mysql.com/downloads/mysql/) and install MySQL
3. Use the Node.js package manager - npm - to install the required Node.js packages.  Running ```npm install``` from the command line will install the following Node.js packages:
    * [mysql2](https://www.npmjs.com/package/mysql2)
    * [express](https://www.npmjs.com/package/express)
    * [express-handlebars](https://www.npmjs.com/package/express-handlebars)
    * [sequelize](https://www.npmjs.com/package/sequelize)

### Sequelize
In the Smöthii application, Sequelize is configured to create database tables based on the Smöthii data models.

### Model-View-Controller File Structure
#### Root directory
* server.js - 
    * requires npm packages
    * allows Sequelize to create tables from models
    * listens to requests to the application on an IP address and PORT
    * defines static routes
    * includes routes to connect requests to resources and serve responses
#### config
* config.json - database configuration file. Can be used to provide local DB configuration or connect to a remote database
#### models
* index.js - used by Sequelize to initialize tables in an empty database
* MODELNAME.js - a separate model file for each database table
#### node_modules
* contains node packages; packages are installed using the node package manager (npm).  See "Installation" section above.
#### public - a static route defined in server.js
* styles - directory with client-available css files
* js - directory with client-available js files
* images - directory of images used by the application
#### routes
* apiRoutes.js - route handling for data requests (return JSON)
* htmlRoutes.js - routes for handling page requests (return HTML)
#### views - 
* *.handlebars templates (are included in {{{body}}} of main.handlebars)
* layouts subdirectory with main.handlebars document template

## Usage
The Smöthii vending interface permits the customer to select from a list of existing Smöthii recipes or create a custom Smöthii.  Once the customer has selected a Smöthii to purchase, a vending interface directs the customer through the purchase and Smöthii production.

##### Key Features of the Application:
* The menu of existing recipes includes pre-configured recipes as well as recipes created by previous customers (all previous custom-made Smöthiis).
* The menu will only permit the customer to select Smöthiis that have sufficient inventory of the recipe ingredients.
* The "create your own" option permits the customer to name and claim their Smöthii creation and use "drag and drop" technology to select 3 ingredients to create a custom concoction.
* Pricing of individual Smöthiis is based on the cost of ingredients.
* Purchasing a Smöthii deducts the required ingredients from the ingredient inventory, updating the availability of Smöthiis based on ingredient inventory.
* Purchases and ingredient restocks are tracked to assist in determining the profitability of the Smöthii vending machine.
* The vending view is configured for a specific screen size for the vending machine screen.

## Technical Notes
* Drag and Drop capability provided through [jquery.ui](https://jqueryui.com/)
* Extension of those capabilities to a touchscreen provided through [jquery.ui.touch-punch.min.js](http://touchpunch.furf.com/)
* To avoid code collisions, each team member deployed working or logically-working code in test files.  Those proofs of concept or working models of the interface were copied into project files and "wired up" to other working components.  As a consequence, the leftover test code has not been removed (and may be in various working states).
* The non-working code is not referenced in the closed working model of the vending interface.
* Known Flaw: If you need to seed an empty database (which we assumed would be a setup state when the vending maching plugged in), navigate to [/test/seed/] and seed the ingredients, smothiis and recipes (in that order).
please don't access that route and add to the live db -- in it's present state it would contnue to add copies of ingredients, potentially overrunning the database or carosel of ingredients in the UI.

## Tools Used:
* HTML5
* CSS3
* Node.js
* JavaScript
* jQuery
* MySQL
* Express
* Sequelize
* Handlebars.js
* Heroku

## Team
The Smöthii development team included:
* Adina
* Antionne
* John
* Sara
* Violet

## Deployed Link
https://smothii.herokuapp.com/
