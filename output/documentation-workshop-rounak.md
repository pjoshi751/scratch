# Documenatation Workshop 

## Overview
This is a trial workshop session to assist us in understanding the guidelines for writing MOSIP related documents.

## Types of documents

### Type 1

_The paragraph below describes admin portal._

Using the admin portal, the administrator can now:

* retrieve an individual's lost or misplaced RID. 
* control the levels of location hierarchy they required while creating the registration centres (the level of the hierarchy can be configured through configuration property value).
* map the users to a registration centre and a zone.
* create and update dynamic fields such as gender, blood type, residence status, marital status etc.
* can now configure the number of kiosks in a particular registration centre during the process of creating one.

### Type 2

_The paragraph below provides the steps to set up the registration client._

#### Step 1: Download TPM utility and run the utility to get machine keys
Please find the instructions to build and run the utility [here](https://github.com/mosip/mosip-infra/blob/develop/deployment/sandbox-v2/utils/tpm/key_extractor/README.md).

#### Step 2: Whitelist the machine keys in the server database
The machine name and keys output from utility should be updated in server. The below API can be used to create / whitelist your machine:

`curl -X POST "https://<HOSTNAME>/v1/masterdata/machine`

NOTE: 
* Replace appropriate value for `HOSTNAME` in the above curl command.
* In case, you are trying to whitelist a non-TPM machine, please set `publicKey` and `signPublicKey` with the same value.

#### Step 3: Create the users in the keycloak with appropriate roles
* Please find the instructions to create the users in keycloak [here](https://www.appsdeveloperblog.com/keycloak-creating-a-new-user/).
* Map the user to the same centre as that of the machine that is created / whitelisted in [Step 2](#step-2-whitelist-the-machine-keys-in-the-server-database).
* Either one of these roles must be assigned to the user in keycloak - "REGISTRATION_SUPERVISOR" or "REGISTRATION_OFFICER".

#### Step 4: Download and start the registration client
Registration client package can be downloaded from the below URL if the enviornment is set up with MOSIP's standard deployment.

`https://{baseURL}/registration-client/{version}/reg-client.zip`
  
