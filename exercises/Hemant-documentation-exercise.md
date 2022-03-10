# Documenatation Workshop 

## Overview
This is a trial workshop session to assist us in understanding the guidelines for writing MOSIP related documents.

## Types of documents

### Type-1

The paragraph below describes admin Portal:
Using the admin portal, the administrator can now retrieve an individual's lost _**rid**_ or _**misplaced rid**_. Using the admin portal, the *admin* can now control the levels of location hierarchy they required while creating the registration centres. The level of the hierarchy can be configured through configuration property value.

Using the admin portal, the administrator can now map the users to a registration centre and a zone using the Admin portal, the administrator can now create and update dynamic fields such as Gender, Blood Type, Residence Status, Marital Status etc. Using the Admin portal, the administrator can now configure the number of kiosks in a particular reg centre during the process of creating the registration centre.

### Type-2 

#### Setting up Registration client

##### Step-1 
Download TPM utility and run the to get machine keys.
Find the instructions to check out, build and run the utility here.

##### Step-2 
Whitelist the machine keys in the server database.
Machine name and keys output from utility should be updated in server.

Use the below API to create or whitelist your machine
<img src= curl -X POST https://<HOSTNAME>/v1/masterdata/machine>

## Note:
_**Replace appropriate hostname in the above curl command
In case of whitelist non TPM machine, set publicKey and signPublicKey with the same value. 
**_
##### Step-3: Know your userId and required roles
  Create the user in the keyCloak.

Map the user to the same centre as that of the machine that is created/whitelisted in Step-2.

Either one of these roles must be assigned to the user in keyCloak - "REGISTRATION_Supervisor, "Reg_OFFICER"
  
##### Step-4. Download registration client and start reg-client
Registration client package can be downloaded from the below URL, if env is set up with MOSIP standard deployment.
 
