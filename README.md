# salesforce-newman
Want to be able to use newman to run a postman collection against Salesforce API

Because Salesforce cannot be run locally - we need to run our integration tests against an actual environment.



# Create a scratch org
You can use ./sfdx-newman to create a scratch org that contains the metadata for the newman test app
- Connected App called 'Newman API'
- //TODO add a script to create newman API user


# Use the Cloudbuild yaml + package.json to run your cloudbuild
Package.json contains dependencies and tests to run example newman builds
Cloudbuild.yaml can setup your CI and execute the tests
