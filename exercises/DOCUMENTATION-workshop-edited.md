# Documentation Workshop 

### Overview
This is a trial workshop session to assist us in understanding the guidelines for writing MOSIP related document.

## Types of documents

### Type1

Using Admin portal,

* The administrator can now retrieve an individual's lost RID or misplaced RID.
* The admin can now control the levels of location hierarchy they required while creating the registration centers. The level of hierarchy can be configured through configuration property value.
* The administrator can now map the users to a registration center and to a zone.
* The administrator can now create and update dynamic fields such as Gender, Blood Type, Residence Status, Marital Status, etc. 
* The administrator can now configure the number of kiosks in a particular registration center during the process of creating the registration center.

### Type 2 

Setting up Registration client:

1. Download TPM utility and run the to get machine keys.
Please find the instructions to check out, build and run the utility [here](https://docs.mosip.io/1.2.0/mosip-documentation-style-guide).

2. Whitelist the machine keys in server db. Machine name and keys output from utility should be updated in server.
Use the below API to create / whitelist your machine
    ```curl -X POST "https://<HOSTNAME>/v1/masterdata/machine```

	NOTE: 
		* Replace appropriate HOSTNAME in the above curl command
		* In case, we are trying to whitelist NON-TPM machine, Please set publicKey and signPublicKey with same value 


  
