File Summaries 
---
package.json : Defines the dependancies needed to run the application. 

server.js : This file is executed to begin running our server. This gathers the routes.js files. The file also declares that we will be using express / and the express session npm packages. The file calls the sequelize.sync() to setup our DB files. Ultimately the file starts the application to liston the the port defined in the PORT variable. 

./config:
config.json : Acts as the configuration and setup for the mySQL databases used within this project. 

passport.js : Requires the models directory. This runs upon loading the page and serves as our method for checking if a user is a registered user. 

---
./config/middleware:
isAuthenticated.js : Handles redirecting unauthenticated / non-registered users. This action is likely called back to in almost all commands used throughout the application to check on the user authentication status. 

---
./models:
index.js : Gathers required node packages & handles some sequelize setup. This will read into our config.json file and get the database connection settings. This then will compile any additional model files ; allowing for the these to be called using db.{modelName}

user.js : Created our user model. The usages of bcryptjs provides password hashing for more secure storage within our mysql database. 

---
./public:
login.html : This is the html template used for the login page. The page provides form input for the user to enter their username and password. --> If the user is not yet registered a link exists to direct the user to the signup. 

members.html : Welcomes a logged in user to the site. Provides an option for the user to logout. 

signup.html : HTML template for signing up a user. This page will take inputs of an email and password. 

---
./public/js:
login.js : Gets the html form elements of the email and password. Assuming both values have been filled out these are then passed to the loginUser function. This sends a data post to the api login with the above username and password. if the users is logged in the user is redirected the /members route. 

members.js : This js file looks up the information about the logged in user (user email) from the API and returns the value to the .member-name class. 

signup.js : Very similar to the login.js file. However instead of signing in an existing user this will instead post to the signup route to create a new user. 

---
./public/stylesheets:
style.css : Defines the css styling used on the application.  

---
./routes:
api-routes.js : This file requires the db models as well as the passport configuration. The file defines what API routes are available for use in the application. 

html-routes.js : This file handles the routing to the applications html files. The file also handles redirecting authenticated vs non-authenticated users. 

