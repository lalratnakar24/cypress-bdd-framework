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
