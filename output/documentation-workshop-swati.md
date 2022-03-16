# Documentation Workshop 

## Overview

This is a trial workshop session to assist us in understanding the guidelines for writing MOSIP-related documentation.

## Types of documents

### Type 1

* Using the Admin portal, the administrator can
    * retrieve an individual's lost RID or the misplaced RID. 
    * control the levels of location hierarchy that are required while creating the Registration Centres.
    * map the users to a Registration Centre and a Zone.
    * create and update dynamic fields such as Gender, Blood Type, Residence Status, Marital Status etc. 
    * configure the number of kiosks in a particular Registration Centre.
        
### Type 2 

#### Setting up the Registration Client

Step 1: Download the TPM utility and run it to get the machine keys.
        Find the instructions to check out, build and run the utility [here].

Step 2: Whitelist the machine keys in server DB. 

* Machine name and keys output from the utility should be updated in the server.
* Use the below API to create your machine.

  `curl -X POST "https://<HOSTNAME>/v1/masterdata/machine"`

_Note_: 
> Replace appropriate HOSTNAME in the above curl command.
> In case, we are trying to whitelist a NON-TPM machine, set the `publicKey` and `signPublicKey` with the same value.

Step 3: Know your userID and required roles. 

* Create the user in the Keycloak. 
* Map the user to same center as that of the machine that is created in the preious step.
* Either one of these roles must be assigned to the user in Keycloak- _REGISTRATION_SUPERVISOR_ or _REGISTRATION_OFFICER_.
  
Step 4: Download the Registration Client package and start the Registration Client setup.

The Registration Client package can be downloaded from the below URL, if environment is setup with MOSIP standard deployment.

URL: "https://github.com/mosip/registration-client.git"
