# SFDMU Excercise 1

This excercise will walk you through a basic org to org data transfer using a simple object structure.
https://help.sfdmu.com/full-documentation/advanced-features/data-anonymization

## Authorize a Dev Hub
This will allow you to create scratch orgs with one serving as the source org where we're getting data from & the other is the target where we are moving data to

## Create one scratch org to serve as the source
This will be the source scratch org and will have the data we wish to transfer to the target

## Run the source scratch org setup script
The script will...
- Install an unlocked package with a simple object model
- Run a data setup script to give our source org data to move

## Create a second scratch org to serve as the target
This will be the target scratch org and will have no data until we move it from the target

## Run the target scratch org setup script
The script will
- Install an unlocked package with a simple object model
- Install link https://login.salesforce.com/packaging/installPackage.apexp?p0=04tHs0000012hZGIAY

# SFDMU Move Operations

sfdx sfdmu:run --sourceusername [sourceorgalias] --targetusername csvfile

## Push data from CSVs to target org
sfdx sfdmu:run --sourceusername csvfile --targetusername [targetorgalias]

## Script Notes
Setup source scratch org: 
sfdx force:org:create -f config\project-scratch-def.json --setalias SFDMU_Source --durationdays 7 --setdefaultusername
sf org generate password
sf package install --package 04tHs0000012hZBIAY
sf org assign permset --name SFDMU_Metadata

