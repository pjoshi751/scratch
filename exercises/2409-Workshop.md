# Documenatation workshop 

### Overview
This is a trial workshop sesion to assist us in underStanding the guidilines for writting MOSIP related document.

## Types of documents

### Type1

_The paragraph below in describes admin Portal_

> Using the admin portal, the administrator can now retrieve an individual's lost or misplaced registration id.
> Control the required levels of location hierarchy while creating the registration centres.
> Map the users to a registration centre and to a zone, create & update dynamic fields such as gender, blood type, residence status, marital status etc.,
> Configure the number of kiosks in a particular reg centre during the process of creating the registration centre.

### Type 2 

_Setting up Registration client_

Step-1: Download the TPM utility and run it to get machine keys. Please find the instructions to check out, build and run the utility here.

Step-2: Whitelist the machine keys in server db. Machine name and keys output from utility should be updated in server.

Use the below api to create / whitelist your machine.
curl -X POST "https://<HOSTNAME>/v1/masterdata/machine"

NOTE : 
> Replace appropriate HOSTNAME in the above curl command.
> In case, we are trying to whitelist NON-TPM machine, Please set publicKey and signPublicKey with same value.

step-3: Know your userId and required roles. Create the user in the keycloak. Map the user to same center as that of the machine that is created/whitelisted in step-2. Either one of these roles must be assigned to the user in keycloak - "REGISTRATION_SUPERVISOR, "REGISTRATION_OFFICER"
  
Step-4: Download registration client and start reg-client. Registration client package can be downloaded from below URL, if environment is setup with MOSIP standard deployment.
URL:"https://github.com/mosip/registration-client.git"
  
