# salesforce-newman
Want to be able to use newman to run a postman collection against Salesforce API

Because Salesforce cannot be run locally - we need to run our integration tests against an actual environment.

Dir Structure
/postman
    /collections   #Postman Test Collections
    /environments  #Postman Environments
/sfdx-newman
    /force-app     #Force-app metadata for Salesforce apps
    package.json   #For Salesforce
package.json

## Target State
Part of a CI build that can do the following:
<ol>
<li>Install NPM
<li>Git checkout an sfdx repo
<li>Run static code analysis (sfdx-cli)
<li>2/ Authorise against a target org (using sfdx-cli)
<li>3/ Run checkdeploy against org
<li>4/ If checkdeploy passes, then deploy
<li><b>5/ Run Newman Collection against Salesforce org to validate they are working as expected<//b>
</ol>


# Create a scratch org
You can use ./sfdx-newman to create a scratch org that contains the metadata for the newman test app
- Connected App called 'Newman API'
- //TODO add a script to create newman API user


# Use the Cloudbuild yaml + package.json to run your cloudbuild
Package.json contains dependencies and tests to run example newman builds
Cloudbuild.yaml can setup your CI and execute the tests


Adding a commit to trigger new CI configuration
