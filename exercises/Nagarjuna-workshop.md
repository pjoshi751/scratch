# Documentation workshop 

### Overview
This is a trial workshop session to assist us in understanding the guidilines for writting MOSIP related document.

## Types of documents

### Type1

Following flows can be achieved by using the admin portal.

* Retrieve an INDIVIDUAL's lost rid or misplaced rid. 
* Controll the levels of location hierarchy they required while creating the registration centres. The level of the hierarchy can be configured through configuration property value.
* Map the users to a registration centre and to a zone
* Create and update dynamic fields such as Gender, Blood Type, Residence Status, Marital Status etc.
* Configure the number of kiosks in a particular reg centre during the process of creating the registration centre.

### Type2 

Setting up Registration client

Step1: Download TPM utility and run the to get machine keys.<br/>
       Please find the instructions to check out, build and run the utility here.

Step2: Whitelist the machine keys in server db.<br/>
       Machine name and keys output from utility should be updated in server.

       Use the below api to create/whitelist your machine.
       curl -X POST "https://<HOSTNAME>/v1/masterdata/machine.

_NOTE : 
      -> Replace appropriate hostname in the above curl command.<br/>
      -> In case, we are trying to whitelist NON-TPM machine, please set publicKey and signpublickey with same value. 

Step3: Know your userId and required roles.<br/>
       Create the user in the keycloak.<br/>
       Map the user to same center as that of the machine that is created/whitelisted in step2.<br/>
       Either one of these roles must be assigned to the user in keycloak - "REGISTRATION_Supervisor, "Reg_OFFICER".
  
Step4: Download registration client and start reg-client.<br/>
       Registration client package can be downloaded from below URL, if env is setup with MOSIP standard deployment.
  
