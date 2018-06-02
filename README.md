<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# How did it all start?

<img src="https://farm1.staticflickr.com/894/40696462890_8ebf943507_z.jpg" width="640" height="308" alt="bitcoinpaper">

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Customer Loyalty Program with Blockchain

This blockchain model for a customer loyalty program enhances the value of points to loyalty program members and brings in new value to the partners. Participants in this network have a more level relation among each other and points are in the centric position to connect all participants.

This code pattern is for developers looking to start building blockchain applications with Hyperledger Composer. When the reader has completed this code pattern, they will understand how to:

* Create basic business network using Hyperledger Composer
* Deploy the network to an instance of Hyperledger Fabric locally and IBM Blockchain
* Build a Node.js web application to interact with the blockchain network using Composer API

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Architecture Flow

<p align="center">
  <img width="650" height="200" src="docs/doc-images/diagram.png">
</p>

1. Member is registered on the network
2. Member can sign-in to make transactions to earn points, redeem points and view their transactions
3. Partner is registered on the network
4. Partner can sign-in to view their transactions and display dashboard


# Hyperledger and Blockchain Components we will be working with

* [Hyperledger Composer v0.19.4](https://hyperledger.github.io/composer/latest/) Hyperledger Composer is an extensive, open development toolset and framework to make developing blockchain applications easier
* [Hyperledger Fabric v1.1](https://hyperledger-fabric.readthedocs.io) Hyperledger Fabric is a platform for distributed ledger solutions, underpinned by a modular architecture delivering high degrees of confidentiality, resiliency, flexibility and scalability.
* [IBM Blockchain Starter Plan](https://console.bluemix.net/catalog/services/blockchain) The IBM Blockchain Platform Starter Plan allows to build and try out blockchain network in an environment designed for development and testing

## Featured technologies
+ [Nodejs](https://www.python.org/) Node.js is an open-source, cross-platform JavaScript run-time environment that executes JavaScript code server-side
+ [Bootstrap](https://getbootstrap.com/) Bootstrap is an open source toolkit for developing with HTML, CSS, and JS

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Create an app in the Hyperledger Composer:

<img src="https://github.com/LennartFr/customer-loyalty-program/blob/master/img/Composer%20Runtime.PNG">

<img src="https://github.com/LennartFr/customer-loyalty-program/blob/master/img/Lets%20Blockchain.PNG">


1. Bring up the Hyperledger Composer Playground: https://composer-playground.mybluemix.net/
1. Import BNA file into the Playground: `clp-network@0.0.1.bna` (In this repo)

Learn the Hyperledger Composer Modeling Language: https://hyperledger.github.io/composer/latest/reference/cto_language.html

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">


# Running the Application

Follow these steps to setup and run this code pattern. The steps are described in detail below.

## Prerequisites
- Operating Systems: Ubuntu Linux 14.04 / 16.04 LTS (both 64-bit), or Mac OS 10.12 or higher
- [Docker](https://www.docker.com/) (Version 17.03 or higher) 
- [npm](https://www.npmjs.com/)  (v5.x)
- [Node](https://nodejs.org/en/) (version 8.9 or higher - note version 9 is not supported)
  * to install specific Node version you can use [nvm](https://davidwalsh.name/nvm)
  
  1. nvm install 8.9
  2. nvm use 8.9 
  3. output: Now using node v8.9.4 (npm 6.1.0)
  
  * Example: 'nvm install 8.94' results in: "Now using Node v8.9.4, NPM v5.6.0"

## 1. Install the Hyperledger Composer runtime components and clone the Customer Loyalty Program GitHub Repo

[Hyperledger Composer](https://hyperledger.github.io/composer/installing/development-tools.html)
  
### Step 1.1  
  * Install composer cli: `npm install -g composer-cli`
  * Install composer-rest-server: `npm install -g composer-rest-server`
  * Install generator-hyperledger-composer: `npm install -g generator-hyperledger-composer`

### Step 1.2
Clone the `Customer Loyalty Program with Blockchain` repo locally. In a terminal, run:

`git clone https://github.com/LennartFr/customer-loyalty-program`

## 2. Generate the Business Network Archive

Next we will generate the Business Network Archive (BNA) file from the root directory.  
This file will contain your network including:
- the model defined in the `org.clp.biznet.cto` file in the `models` folder
- the logic behind transactions in the `logic.js` file in the `lib` folder
- permissions defined in the `permissions.acl` file
- queries defined in the `queries.qry` file

Run the following command to create the BNA file:
```
cd customer-loyalty-program/
npm install
```

The `composer archive create` command in `package.json` has created a file called `clp-network@0.0.1.bna`.   


## Step 3. Deploy the Business Network

The BNA file can either be deployed to a local instance of Fabric or to the IBM Blockchain Starter Plan.

- [To deploy to Hyperledger Fabric locally, please click here](./docs/deploy-local-fabric.md)
- [Or to deploy to IBM Blockchain Starter Plan, please click here](./docs/deploy-ibm-starter.md)

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

## Step 4. Run the Application
At this point you will either have installed the Hyperledger Fabric locally or to the IBM Blockchain Starter Plan!
See above for the instructions.

Go into the `web-app` folder and install the dependency:

```
cd web-app/
npm install
```

Start the application:
```
npm start
```

The application should now be running at:
`http://localhost:8000`

<div style='border: 2px solid #f00;'>
  <img width="1000" src="docs/doc-images/app.png">
</div>
</br>

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

### Deploy application to the IBM Cloud

If your hosting the network on IBM Blockchain Starter Plan, then you can [deploy the app to IBM Cloud](./docs/deploy-app-cloud.md).

## Links
* [Hyperledger Fabric Docs](http://hyperledger-fabric.readthedocs.io/en/latest/)
* [Hyperledger Composer Docs](https://hyperledger.github.io/composer/latest/introduction/introduction.html)

## License
[Apache 2.0](LICENSE)
