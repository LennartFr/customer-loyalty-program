<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Customer Loyalty Program with blockchain

This blockchain model for a customer loyalty program enhances the value of points to loyalty program members and brings in new value to the partners. Participants in this network have a more level relation among each other and points are in the centric position to connect all participants.

In this code pattern, we will create a customer loyalty program as a blockchain application using Hyperledger Composer API and Node.js. The application will allow members to register on the network where they will create their account.  They will be identified on the network with their account number and will create a access key which they will use to sign in.  This access key is used as the card id for the member to make transactions and query records.  The member once signed in, can make transactions to earn points and redeem points from the partners on the network. They can view their transactions as part of the blockchain ledger.  This code pattern illustrates the use of permissions as part of the network where a member can only view their transactions.

Similarly for the partner, they will register by creating an identity on the network and an access key which will be used to view their records.  Partners are allowed to view only transactions they were part of, and thus can keep track of all their transactions where they allocated or redeemed points.  The application shows a basic dashboard for the partner displaying the total points that they have allocated and redeemed to members.  As transactions get complex, the partner can perform analysis on their transactions to create informative dashboards.

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

## Featured technology
+ [Nodejs](https://www.python.org/) Node.js is an open-source, cross-platform JavaScript run-time environment that executes JavaScript code server-side
+ [Bootstrap](https://getbootstrap.com/) Bootstrap is an open source toolkit for developing with HTML, CSS, and JS

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Installing the Application

# Lennart: Cleanup commands:

https://stackoverflow.com/questions/48365524/uninstall-hyperledger-composer

Before we begin the install process we want to make certain that we remove any components that can collide with
what we are going to install.

So please run the following commands:

Run these commands below to stop and remove container processes.

- docker stop $(docker ps -a -q)
- docker rm $(docker ps -a -q)

To stop and remove images completely run the following commands

- docker stop $(docker images -a -q)
- docker rmi $(docker images -a -q)
- docker ps -a
- docker images -a

- npm uninstall -g composer-cli
- npm uninstall -g composer-rest-server
- npm uninstall -g generator-hyperledger-composer
- npm uninstall -g yo
- npm uninstall -g composer-pla
- npm uninstall -g composer-cli
- npm uninstall -g composer-rest-server

- rm -rf ~/.composer
- rm *.card
- rm -rf credentials
- rm -fr ${HOME}/.composer


Follow these steps to setup and run this code pattern. The steps are described in detail below.

## Prerequisites
- Operating Systems: Ubuntu Linux 14.04 / 16.04 LTS (both 64-bit), or Mac OS 10.12
- [Docker](https://www.docker.com/) (Version 17.03 or higher)
- [npm](https://www.npmjs.com/)  (v5.x)
- [Node](https://nodejs.org/en/) (version 8.9 or higher - note version 9 is not supported)
  * to install specific Node version you can use [nvm](https://davidwalsh.name/nvm)
- [Hyperledger Composer](https://hyperledger.github.io/composer/installing/development-tools.html)
  * to install composer cli
    `npm install -g composer-cli`
  * to install composer-rest-server
    `npm install -g composer-rest-server`
  * to install generator-hyperledger-composer
    `npm install -g generator-hyperledger-composer`


## 1. Clone the repo

Clone the `Customer Loyalty Program with Blockchain` repo locally. In a terminal, run:

`git clone https://github.com/IBM/Customer-Loyalty-Program`

## 2. Generate the Business Network Archive

Next we will generate the Business Network Archive (BNA) file from the root directory.  
This file will contain your network including:
- the model defined in the `org.clp.biznet.cto` file in the `models` folder
- the logic behind transactions in the `logic.js` file in the `lib` folder
- permissions defined in the `permissions.acl` file
- queries defined in the `queries.qry` file

Run the following the command to create the bna file:
```
cd customer-loyalty-program/
npm install
```

The `composer archive create` command in `package.json` has created a file called `clp-network@0.0.1.bna`.   


## 3. Deploy the Business Network

The bna can either be deployed to a local instance of Fabric or to the IBM Blockchain Starter Plan.


- [Either deploy to Hyperledger Fabric locally, please click here](./docs/deploy-local-fabric.md)
- [Or deploy to IBM Blockchain Starter Plan, please click here](./docs/deploy-ibm-starter.md)

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

## 4. Run the Application
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

# Lennart Note:  https://stackoverflow.com/questions/48804166/composer-runtime-install-error-card-not-found-peeradmin

When you run the program and create Member Registration you will get the following error:

https://stackoverflow.com/questions/48804166/composer-runtime-install-error-card-not-found-peeradmin

<div style='border: 2px solid #f00;'>
  <img width="1000" src="docs/doc-images/app.png">
</div>
</br>

### Deploy application to the IBM Cloud

If your hosting the network on IBM Blockchain Starter Plan, then you can [deploy the app to IBM Cloud](./docs/deploy-app-cloud.md).

## Links
* [Hyperledger Fabric Docs](http://hyperledger-fabric.readthedocs.io/en/latest/)
* [Hyperledger Composer Docs](https://hyperledger.github.io/composer/latest/introduction/introduction.html)

## License
[Apache 2.0](LICENSE)
