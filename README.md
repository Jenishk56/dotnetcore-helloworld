# Deployment Process :-
- Using the Azure DevOps from -> https://azure.microsoft.com/en-gb/services/devops creating the Sample pipeline.
- Creating a private project in there with name - dotnetcore-helloworld
- Generating the Webhook with github for the deployment on trigger.
- This will provide the azure-pipeline.yml template.

I created the automated pipeline using the Build Pipeline and the Release Pipeline.
On every commit, the Build would get executed and at any stage if it gets failed, other steps will get skipped automatically.

The stages been involved in the Azure pipeline :-

# Build :-
- Checkout
- Build of the API Dotnet App
- Unit Tests
- Code coverage of the Testcase
- Publish the code coverage
- Build and Deploy the artefact at the "drop" location.
# Please refer file - azure-pipeline.yml

# Deployment :-
- Pickup the artefact (From drop location)
- Deploy the artefact in a Azure App environment
  - Download the artefact and put it at -> d:\a\r1\a
  - Execute the server and expose the api at the IP of the VM.
# Please refer file - Release-Pipeline.json & deployment.yml

# The Deployment will pickup the latest artefact of the Master branch Build.
# The Deployment will happen on every night 3 AM if there is any change in a particular Day.

This was my first attempt with the Dotnet Application. And I thoroughly enjoyed developing this end to end pipeline.
