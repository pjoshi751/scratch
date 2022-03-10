# Documentation Workshop

## Overview
This is a trial workshop session to assist us in understanding the guidelines for writing MOSIP related document.

## Types of documents

### Type 1

The paragraph below describes Admin Portal

- Using the admin portal, the _admin_ can now
  - retrieve an individual's lost RID or misplaced RID. Using the admin portal.
  - control the levels of location hierarchy they require while creating the registration centres. The level of the hierarchy can be configured through configuration property value.
  - map the users to a registration centre and to a zone
  - create and update dynamic fields such as Gender, Blood Type, Residence Status, Marital STATUS etc.
  - configure the number of kiosks in a particular reg centre during the process of creating the registration centre.

### Type 2

Setting up Registration client

1. Download [TPM utility](). Check out, build and run the `getMachineKeys` utility.
1. Whitelist the machine keys in server DB.
Machine name and keys output from utility should be updated in server.
1. Use the below API to create / whitelist your machine
```
curl -X POST "https://<HOSTNAME>/v1/masterdata/machine
```
  NOTES :
  - Replace appropriate `<HOSTNAME>` in the above curl command.
  - In case, you are trying to whitelist NON-TPM machine, set `publicKey` and `signPublicKey` with same value.
1. Know your userId and required roles. Create the user in the Keycloak.
1. Map the user to same center as that of the machine that is created/whitelisted in Step-2.
1. Either one of these roles must be assigned to the user in Keycloak - `REGISTRATION_Supervisor`, `Reg_OFFICER`
1. Download [Registration Client]() and start it.
