# Documenatation Workshop 

## overview
This is a trial workshop session to assist you, make under-standing the guidelines for writing mosip-related document.

## types of documents

### type1

Points below will describe about Admin Portal :

	1. Using Admin Portal, administrator can retrieve an individual lost rid or misplaced rid. 
	2. Using Admin Portal, administrator can control levels of location hierarchy they required while creating registration centre. The level of 	hierarchy can be configured through configuration property value.
	3. Using Admin Portal, administrator can map users to a registration centre and a zone.
	4. Using Admin Portal, administrator can create and update dynamic fields such as Gender, Blood Type, Residence Status, Marital Status etc. 
	5. Using Admin Portal, administrator can configure number of kiosks in a particular registration centre during the process of creating registration centre.

### type2 

Setting up Registration Client :

Step1: Download TPM utility and run the to get machine keys
Please find the instructions to check out, build and run the utility here

Step2: Whitelist the machine keys in server db
Machine name and keys output from utility should be updated in server.

use the below api to create / whitelist your machine
curl -X POST "https://<HOSTNAME>/v1/masterdata/machine

NOTE : 
-> Replace appropriate HOSTNAME in the above curl command
-> In case, we are trying to whitelist NON-TPM machine, Please set publicKey and signPublicKey with same value 

step3: Know your userId and required roles
  Create the user in the keycloak.

Map the user to same center as that of the machine that is created/whitelisted in Step-2.

Either one of these roles must be assigned to the user in keycloak - "REGISTRATION_Supervisor, "Reg_OFFICER"
  
Step4: Download registration client and start reg-client
Registration client package can be downloaded from below URL, if env is setup with mosip standard deployment.
  
