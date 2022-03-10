# Documenatation Workshop 

# Overview
This is a trial workshop session to assist us in understanding the guidelines for writing MOSIP related documents.

## Types of documents

### Type1: The paragraph below describes admin portal

Using the admin portal, the administrator can now 
* retrieve an individual's lost rid or misplaced rid. 
* control the levels of location hierarchy they required while creating the registration centres. The level of the hierarchy can be configured through configuration property value.
* map the users to a registration centre and a zone.
* create and update dynamic fields such as gender, blood type, residence status, marital status etc.
* can now configure the number of kiosks in a particular reg centre during the process of creating the registration centre.

### Type 2: Setting up the registration client

#### Step 1: Download TPM utility and run the to get machine keys
Please find the instructions to build and run the utility [here](https://github.com/mosip/mosip-infra/blob/develop/deployment/sandbox-v2/utils/tpm/key_extractor/README.md).

#### Step 2: Whitelist the machine keys in the server database
The machine name and keys output from utility should be updated in server.

Use the below API to create / whitelist your machine
`curl -X POST "https://<HOSTNAME>/v1/masterdata/machine`

NOTE: 
* Replace appropriate HOSTNAME in the above curl command.
* In case, we are trying to whitelist non-TPM machine, please set `publicKey` and `signPublicKey` with the same value.

#### Step 3: Create the users in the keycloak and add appropriate roles
* Please find the instructions to create the users in keycloak using the instructions [here](https://www.appsdeveloperblog.com/keycloak-creating-a-new-user/).
* Map the user to the same centre as that of the machine that is created/whitelisted in Step-2.
* Either one of these roles must be assigned to the user in keycloak - "REGISTRATION_SUPERVISOR, "REGISTRATION_OFFICER".

#### Step 4: Download registration client and start the registration client
Registration client package can be downloaded from the below URL if env is set up with MOSIP standard deployment.
`https://{baseURL}/registration-client/{version}/reg-client.zip`
  
