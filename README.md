Yobichain
=========

> WARNING: Yobichain is intended for experimenting and learning, NOT for production environment.

YobiChain is your very own private blockchain ecosystem preloaded with development tools, database, web & FTP server and a simple blockchain application. To know more, visit http://www.primechain.in/yobichain.php

YobiChain is ideal for

* Startups looking to quickly build a blockchain powered prototype, PoC or MVP
* Serious researchers / enthusiasts looking to experiment with a live blockchain
* In-house teams experimenting with blockchain technology

This version of Yobichain runs on [Multichain](https://github.com/MultiChain) 

    Copyright(C) 2017 by Primechain Technologies Pvt. Ltd.
    License: GNU General Public License version 3

System Requirements
-------------------

One server (min 2 GB RAM, 2 CPUs) running Ubuntu 16.04.2 x64 and latest version of phpMyAdmin. You can set this up using Digtal Ocean's one-click app - PhpMyAdmin on 16.04. Use this link to get a free $10 credit from Digital Ocean: https://m.do.co/c/dc0df9a8a187 

Installation
------------

This section presumes that you have root permission and want to install Yobichain for all users on the system.

Install git and clone the yobichain repository

    sudo apt-get install git
    sudo git clone https://github.com/Primechain/yobichain.git

Harden the base operating system. This will also create a new user called yobiuser with the password entered by you below.

    cd yobichain
    sudo bash -e hardening.sh <password>

Install the FTP server. This will set up the FTP server. For logging in use the IP address of your server as the `host`. The username and password are as entered by you below. The connection is `SFTP`.

    sudo bash -e ftp.sh <username> <password>


Install, configure and run the Multichain blockchain, Multichain web-demo and Multichain Exporer. This also sets up docHash, a simple drag n drop solution for authenticating and verifying electronic records.

    sudo bash -e multichain.sh <chain-name> <rpc-username> <rpc-password>
		
To access Multichain web-demo, visit to `http://<IP Address>/multichain-web-demo`

To access Multichain Exporer, visit to `http://<IP Address>:2750`

To use docHash, 
* Go to `http://<IP Address>/hashchain/hashchain_authenticator.php` and drag and drop any file (text, doc, pdf, video anything). 
* The hash of the file will be immediately calculated in your browser. 
* This hash will then be uploaded to your blockchain and stored. 
* To verify, go to `http://<IP Address>/hashchain` and drag and drop a file. 
* If the hash of that file exists in your blockchain, the file will show as verified. If not, it will show as not verified.


Notes
-----

This will:
* harden the base operating system against cyber attacks
* set up a Multichain blockchain using a pre-defined configuration
* set up PHPmyadmin, PHP, MySQL and Apache
* set up Multichain web demo
* set up Multichain Explorer
* set up docHash, a simple drag n drop solution for authenticating and verifying electronic records.


In case something goes wrong, you can roll back the multichain installation using

    bash rollback_multichain.sh 

Live demo
---------
* To access Multichain web-demo, visit http://139.59.64.145/multichain-web-demo
* To access Multichain Exporer, visit http://139.59.64.145:2750
* To authenticate a file using docHash, visit http://139.59.64.145/hashchain/hashchain_authenticator.php 
* To verify a file using docHash, visit http://139.59.64.145/hashchain/ 

Planned roadmap
-----
* Installation of other blockchains and distributed ledger systems BigChainDB, Chain, Corda, Credits, Elements, Eris, Fabric, Ethereum, HydraChain, Hyperledger, Openchain, Quorum, Sawtooth, Stellar.
* Installation of MEAN (MongoDB, Express, AngularJS, Node.js)
