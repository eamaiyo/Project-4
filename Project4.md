## Documentation for Project 4
## MEAN STACK DEPLOYMENT TO UBUNTU IN AWS

## STEP 1 — Install NodeJs

-- Starting by spinning up an EC2 instance server labelled 'Projec 4 - MEAN' from my CLI terminal in AWS

`sudo apt update`--(running command to update my list of packages in Ubuntu package manager)
![BackendConfig-Update](./Image-4/Ubuntu-Install-Update-1.PNG)

`sudo apt upgrade`--(running command to upgrade to lastest list of packages in Ubuntu package manager)
![BackendConfig-Upgrade](./Image-4/Ubuntu-Install-Upgrade-2.PNG)

`sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates`--(Add certificates)
![Ubuntu-Add-Certifcate-3a](./Image-4/Ubuntu-Add-Certifcate-3a.PNG)

`curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -` -(Add certificates)
![Ubuntu-Add-Certifcate-3b](./Image-4/Ubuntu-Add-Certifcate-3b.PNG) 

`sudo apt install -y nodejs` -(Installing Node.js to make my system and broswer act as a server)
![Ubuntu-Install-Nodejs](./Image-4/Ubuntu-Install-Nodejs-4.PNG)

## STEP 2 — INSTALL MONGODB

`sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6` ;`echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list`--(adding book records to MongoDB that contain book name, isbn number, author, and number of pages.mages/WebConsole.gif)
![Mongo-AddBookRecords](./Image-4/Mongo-AddBookRecords-1.PNG)

`sudo apt install -y mongodb` --(Installing mongodb database to store and retrieve data)
![Mongo-Install-MongoDB](./Image-4/Mongo-Install-MongoDB-2.PNG)

`sudo systemctl start mongodb` --(Start The server)
![Mongo-Install-MongoDB](./Image-4/Mongo-StatusMongoDB-3.PNG)

`sudo systemctl status mongodb` --(Verify that the service is up and running)
![Mongo-StatusMongoDB](./Image-4/Mongo-StatusMongoDB-3.PNG)

`sudo  npm install body-parser` --(Installing "body-parser" package to help process JSON files passed in requests to the server)
![Mongo-Install-BodyParser](./Image-4/Mongo-Install-BodyParser-4.PNG)

`mkdir Books && cd Books` ; `npm init`--(Create folder "Books" which is our project directory then initializing Books project)
![Mongo-CreateBooks-initBooks](./Image-4/Mongo-CreateBooks-initBooks-5.PNG)

`vi server.js` --(Create folder "Books" which is our project directory then initializing Books project)
![Mongo-configFile-server.js](./Image-4/Mongo-configFile-server.js-6.PNG)


## STEP 3 — INSTALL EXPRESS AND SET UP ROUTES TO THE SERVER

`sudo npm install express mongoose`--(1. Install Express - Node framework and define routes for application base of http method and url. 2. Mongoose - use to model application data)
![Express-Install-ExpressMongoose](./Image-4/Express-Install-ExpressMongoose-1.PNG)

`mkdir apps && cd apps && touch routes.js`--(Create folder "apps" within Books project directory and create a file routes.js in the apps folder)
![Express-CreateApps-Routes.jsFile](.Image-4/Express-CreateApps-Routes.jsFile-2.PNG)

`vi routes.js`--(Open the routes.js file using vi text edior for linux environment, copy and paste snippet application code)
![Express-Config-Routes.jsFile](./Image-4/Express-Config-Routes.jsFile-3.PNG)

`mkdir models && cd models && touch book.js`--(Create folder "models" within Books project directory and create a file book.js in the models folder)
![Express-CreateModels-Book.jsFile](./Image-4/Express-CreateModels-Book.jsFile-4.PNG)

`vi book.js`--(Open the book.js file using vi text edior for linux environment, copy and paste snippet application code)
![Express-Config-Book.jsFile](./Image-4/Express-Config-Book.jsFile-5.PNG)

## STEP 4 – ACCESS THE ROUTE WITH ANGULARJS 

`mkdir public && cd public && touch script.js`--(Create folder "public" within Books project directory and create a file script.js in the public folder)
![AccessRouteAngular-CreatePublic-Script.jsFile](./Image-4/AccessRouteAngular-CreatePublic-Script.jsFile-1.PNG)

`vi script.js`--(Open the script.js file in public diretory using vi text edior for linux environment, copy and paste snippet application code)
![AccessRouteAngular-Config-Script.jsFile](./Image-4/AccessRouteAngular-Config-Script.jsFile-2.PNG)

`vi imdex.html`--(Controller configuration defined. Open the script.js file in public diretory using vi text edior for linux environment, copy and paste snippet application code )
![AccessRouteAngular-Config-Index.htmlFile](./Image-4/AccessRouteAngular-Config-Index.htmlFile-3.PNG)

`node server.js`--(Start the server by running, confirmation server is runnning on TCP port 3300)
![AccessRouteAngular-Start-Server](./Image-4/AccessRouteAngular-Start-Server-4.PNG)

`node server.js`--(Start the server by running)
![AccessRouteAngular-Start-Server](./Image-4/AccessRouteAngular-Start-Server-4.PNG)

`http://100.26.224.20:3300`--(Access our Book Register web application from the Internet with a browser using Public IP address or Public DNS name. Post some entry which was stored in the database and retrieving entry list by hitting enter key on keyboard)
![Test-WebBookApp-Test-Browser](./Image-4/Test-WebBookApp-Test-Browser-5.PNG)

`curl -s http://169.254.169.254/latest/meta-data/public-ipv4`;`curl -s http://169.254.169.254/latest/meta-data/public-hostname` --(Retrieving my server Public IP address and Publid DNS name from my CLI terminal on aws.Testing how to retrieve files content in my meta-data directory.
![Test-Metadata-PublicIP-PublicDnsName](./Image-4/Test-Metadata-PublicIP-PublicDnsName-6.PNG)