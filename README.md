<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">


# Introduction
Published October 2008.<p>

<img src="https://github.com/LennartFr/customer-loyalty-program/blob/master/img/Harvard%20Business%20Review.PNG">

# How it all started
<p>
October 2008 It all started with Satoshi Nakamoto and his paper [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf) 
which addressed a key problem in electronic commerce:
<h3>
<b> 
 
~~~
A purely peer-to-peer version of electronic cash would allow online payments
to be sent directly from one party to another without going through a financial 
institution. 

Digital signatures provide part of the solution, but the main benefits are lost 
if a trusted third party is still required to prevent double-spending.

We propose a solution to the double-spending problem using a peer-to-peer network.
~~~

</b>
</h3>


## Background to Blockchain, Connected Markets. <p>
Networks connect participants: customers, suppliers, banks, consumers
 * <b>Markets </b> organize trades: Public and private markets
 * Value comes from <b>assets</b>: Physical assets (house, car ...), Virtual assets (bond, patent ...), Services are also assets
 * <b>Transactions </b> exchange assets 

An asset can be tangible — a house, a car, cash,  land  —  or  intangible  like  intellectual  property,  such  as 
patents, copyrights, or branding. Virtually anything of value can be tracked and traded on a blockchain network, reducing risk and 
cutting costs for all involved.
<p>
 <p>
 https://www.itu.int/en/ITU-T/Workshops-and-Seminars/201703/Documents/Christian%20Cachin%20blockchain-itu.pdf
<p>
A blockchain is a <b>decentralized virtual ledger</b> for recording <b>transactions about assets </b> without <b>central authority</b> through a <b>distributed cryptographic protocol</b>. 
<p>
 The blockchain ledger is permissioned, it supports consensus, it has provenance, immutability and finality.

## The Blockchain Distributed Ledger

<img src="https://www.ibm.com/blogs/internet-of-things/wp-content/uploads/2017/05/2-1.jpg">
<p>
 
<b>Anything that you can make a list of, you can manage with blockchains</b> 

## Four elements characterize Blockchain

### Replicated ledger
* History of all transactions
* Append-only with immutable past
* Distributed and replicated
 
### Cryptography
* Integrity of ledger
* Authenticity of Transactions
* Privacy of Transactions
* Identity of Participants

### Consensus
* Decentralized Protocol
* Shared conrol tolerating disruption
* Transactions validated

### Business Logic
* Logic embedded in the ledger
* Executed together with transactions
* From simple "coins" to self-enforcing "smart contracts" 
                       
<p>
which combined provide a trustworthy service to a group of nodes that do not fully trust each other. 
<p>
With blockchain, several users can write entries into a block or a record of information, and a community can control how the record of information is modified and updated.

[E-book Blockchain for Dummies](https://www-01.ibm.com/common/ssi/cgi-bin/ssialias?htmlfid=XIM12354USEN)
<p>

# Bockchain concepts

## The Ledger and the State Database

There are two place which "store" data in Hyperledger Fabric:
### The ledger is the actual "blockchain". 
It is a file-based ledger which stores serialized blocks. Each block has one or more transactions. <br>
Each transaction contains a read-write set which modifies one or more key/value pairs. <br>
The ledger is the definitive source of data and is immutable.

### The state database holds the last known committed value for any given key. 
It is populated when each peer validates and commits a transaction. <br>
The state database can always be rebuilt from re-processing the ledger. <br>
There are currently two options for the state database: an embedded LevelDB or an external CouchDB.
<p>
As an aside, if you are familiar with Hyperledger Fabric channels, there is a separate ledger for each channel as well.
<p>
When we query from where do we retrieve data?  1) from the blockchain chain or 2) from state db? <p>.
If it is from state db how can it retrieve a specific key because you mentioned "state database holds the last known committed value for any given key" <p> 
Queries or GetState in chaincode return data from the state db. They will only return the last value for a key. <p>
If you want to get the entire history for a key, you need to enable the historical database in the configuration of your peer 

### Chaincode.
Like <b>Stored Procedures</b> in a traditional database, handles business logic. http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.htm




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

## Architecture

<img src="https://github.com/LennartFr/customer-loyalty-program/blob/master/img/Composer%20Runtime.PNG">

## Composer Starting Page

<img src="https://github.com/LennartFr/customer-loyalty-program/blob/master/img/Lets%20Blockchain.PNG">

### Upload BNA file by down-arrow.
<img src="https://github.com/LennartFr/customer-loyalty-program/blob/master/img/Composer2.PNG">

### Deploy BNA File
<img src="https://github.com/LennartFr/customer-loyalty-program/blob/master/img/Composer3.PNG">

### Connect Business Network Archive
<img src="https://github.com/LennartFr/customer-loyalty-program/blob/master/img/Composer5.PNG">

### Readme
<img src="https://github.com/LennartFr/customer-loyalty-program/blob/master/img/Composer8.PNG">


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
