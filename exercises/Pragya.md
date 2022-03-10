# Scratch
This is a temporary repository for documentation training.
# Documentation workshop 

## Overview
This is a trial workshop session to assist us in understanding the guidelines for writing MOSIP related document.

## Types of documents:

### Type 1:

_The below paragraph describes the Admin Portal_:

Using the admin portal, the administrator can now retrieve an individual's lost rid or misplaced rid. Using the admin portal, the *admin* can now control the levels of location hierarchy they required while creating the registration centres. The level of the hierarchy can be configured through configuration property value.
Using the admin portal, the administrator can now map the users to a registration centre and to a zone.
Using the Admin portal, the administrator can now create and update dynamic fields such as Gender, Blood Type, Residence Status, Marital Status etc. using the admin portal, the administrator can now configure the number of kiosks in a particular reg centre during the process of creating the registration centre.

### Type 2:

_Setting up Registration Client_:

Follow the below steps to setup the Registration Client:

**Step 1**. Download TPM utility and run to get machine keys.
Please find the instructions to check out, build and run the utility here.

**Step 2**. Whitelist the machine keys in server db.
Machine name and keys output from utility should be updated in server.

Use the below API to create / whitelist your machine:

    curl -X POST "https://<HOSTNAME>/v1/masterdata/machine

**NOTE**: 
Replace appropriate _hostname_ in the above curl command.
In case, we are trying to whitelist non-TPM machine, please set publicKey and signPublicKey with same values.

**Step 3**. Know your user Id and required roles and follow the below steps:
  
    1. Create the user in the keycloak.

    1. Map the user to same center as that of the machine that is created/whitelisted in Step 2.

    1. Either one of these roles must be assigned to the user in keycloak: "REGISTRATION_Supervisor, "Reg_OFFICER".
  
**Step 4**. Download registration client and launch it.
Registration client package can be downloaded from below URL, if env is setup with MOSIP standard deployment.
  
    URL: https://qa-double-rc2.mosip.net/
  
