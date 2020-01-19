# Arabic Speaking (Egyptian Slang) Banking Chatbot

# Introduction
In this  tutorial, I'll go through the steps to import a Watson Assistant workspace using the Watson™ Assistant API.

# Facebook Integration
The below Repo is a key to complete integrating the Chatbot with Facebook 
https://github.com/watson-developer-cloud/botkit-middleware
You will just need to follow it's instructions

# Background and Pre-Req
Teams working to build a virtual agent with Watson Assistant will define the agent’s domain using intents and entities, then structure the agent’s ability to converse through a dialog. The aforementioned intents, entities, and dialog are the core components of a Watson Assistant workspace, and it’s this workspace that a development team will look to version and promote as they build and deploy a virtual agent solution. The Watson Assistant API makes it easy to both export and import a Watson Assistant workspace. The instructions provided here can be used to create a duplicate of an existing workspace that can be used for training, development, testing, etc.

# Retrieve workspace ID
Before exporting a particular workspace, we first need the workspace ID that can be obtained from the Watson Assistant UI on IBM Cloud or through the Watson Assistant API.

To retrieve a workspace ID using the Watson Assistant API, issue the following curl command:

curl -u "{username}":"{password}" "https://gateway.watsonplatform.net/assistant/api/v1/workspaces?version=2018-09-20"

Show more
Replace {username} and {password} in the command above with the appropriate credentials for your Watson Assistant instance. You might notice that your Watson Assistant instance doesn’t use username/password as a means of authentication, but instead uses an Identity and Access Management (IAM) API Key. In this case replace "{username}":"{password}" with "apikey:{apikey}" where {apikey} is the IAM API key value for the Watson Assistance service instance.

The URL used in the command above is for use with a Watson Assistant service instance running in the U.S. South region. Update the URL to the appropriate value for your Watson Assistant instance; this will alter based on region and can be found on the same page as your service credentials from IBM Cloud.

# Import Watson Assistant workspace
In this last step, we’ll import a Watson Assistant workspace into another instance of Watson Assistant. To import a Watson Assistant workspace, issue the following command:

curl -H "Content-Type: application/json" -X POST -u "{username}":"{password}" -d @workspace.json "https://gateway.watsonplatform.net/assistant/api/v1/workspaces?version=2018-09-20"

Show more
As before, we’ll alter the command above to use an IAM API key if required and update the URL for our Watson Assistant instance if needed. Remember, we can import the Watson Assistant workspace from the workspace.json file to the same Watson Assistant instance or another instance as needed. After importing your Watson Assistant workspace, you may decide to change the workspace name to identify a workspace version or release phase; this workspace name change can be completed from the Watson Assistant UI after import.

Summary
Following the steps above, You can import the JSON file which is the asset into WA.
