cypressAutomation
#Instalation

Download and install NodeJS from official site. https://nodejs.org/en/download/ for Mac- macOS Installer (.pkg) 64-bit / ARM64
check the path is set. echo $PATH /usr/local/bin- should be in path If not set as below if not the do below
sudo nano /etc/paths?? enter passoword>> insert a line and add path
Hit control-x to quit. Enter “Y” to save the modified buffer.
check with echo $PATH
Download and visual Studio

mkdir foldername >> cd foldername

npm -i init (just hit enter for everyline without changing any values for now.) Package.json will get created- metadata related to the project. It is same like .xml file in maven to manage dependenciew.

Click in visual studio Open folder and add that filder you have created

Install cypress using npm.-- npm intall cypress to add it in package.json file npm intall cypress --save-dev

Running test runner

Now you have the cypress install anf you will see a folder is created in your project- go to terminal and pass this command ~/CypressAutomation/node_modules/.bin/cypress open

now a browser will open, select E2E testing

Configuration files will be displayed in the next screen

click on continue >> select the browser you want to run test on

Now the test runner is running.

create a test.js file under integration/examples

Check a file by name cypress.config.js in project folder. It contains const { defineConfig } = require("cypress");

module.exports = defineConfig({ e2e: { setupNodeEvents(on, config) { // implement node event listeners here }, }, }); 7. add a line in that- specPattern: 'cypress/integration/examples/*.js' (the new content will look like below)

const { defineConfig } = require("cypress");

module.exports = defineConfig({ e2e: { setupNodeEvents(on, config) { // implement node event listeners here }, specPattern: 'cypress/integration/examples/*.js' }, });

*.js is used to read all the spec in the path mentioned 8. Save the file and now you will see the specs which are nothing but test.


***************************************************************************************************************************************

1. install cypress cucumber preprocessor
npm install @badeball/cypress-cucumber-preprocessor

2. add the details in cypress config in setUpnodeevents.
 in the github page if you click on docs and then click on examples you will find the example config in 
cypress-cucumber-preprocessor/examples/browserify-cjs/cypress.config.js 

also add preprocessor in config.js

const preprocessor = require("@badeball/cypress-cucumber-preprocessor");
const browserify = require("@badeball/cypress-cucumber-preprocessor/browserify");


3. go to package.json it is javascript compilation plugin

cypress-cucumber-preprocessor/examples/browserify-cjs/package.json
and take the dependency of browserify
    "@cypress/browserify-preprocessor": "latest",
add this in your project package.json

4. type visual studio cucumber bdd extension
select cucumber(gherkins) full support
install this.

5. create a feature file in folder integration/your projectfolder/ with extension .feature

the feature file will look for the specs in folder with same name as the feature. 
Create a folder with same name as your feature file but without .feature extension.
In this folder you can write all the specs.


4. change the specpattern path to .feature file

7. Keep the hooks in a separate file in same folder where you keep specs
  create a file with beforeEach(). This is mocha hook and BDD supported by cucumber.

beforeEach will execute for every test where as #before will execute only once.

Important if you are using mocha hook then flat operator ()=> can not be used instead use function() specially in that funtion rest places you can use flat operator too.

Importing pageobject
your page object is keot in this folder

r$ '/Users/lalratnakar/CypressFramework/cypress/support/pageObjects/HomePage.js'

your specs are in 

/Users/lalratnakar/CypressFramework/cypress/integration/examples/BDD/ecommerce/eCommStepDef.js'

so your spec has to travel 4 folder up to go to support and then read the file

To run with tag
npx cypress run --env tags="@Regression" --headed --browser chrome
**************************************************************
