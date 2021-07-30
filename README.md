# salesforce-newman
Want to be able to use newman to run a postman collection against Salesforce API

Because Salesforce cannot be run locally - we need to run our integration tests against an actual environment.


## Target State
Part of a CI build that can do the following:

0/ Install NPM
1/ Git checkout an sfdx repo
2/ Run static code analysis (sfdx-cli)
2/ Authorise against a target org (using sfdx-cli)
3/ Run checkdeploy against org
4/ If checkdeploy passes, then deploy
5/ Run Newman Collection on your APIs to validate they are working as expected in Production


# Create a scratch org
You can use ./sfdx-newman to create a scratch org that contains the metadata for the newman test app
- Connected App called 'Newman API'
- //TODO add a script to create newman API user


# Use the Cloudbuild yaml + package.json to run your cloudbuild
Package.json contains dependencies and tests to run example newman builds
Cloudbuild.yaml can setup your CI and execute the tests
