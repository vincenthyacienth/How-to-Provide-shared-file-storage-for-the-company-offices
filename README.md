# How To Provide Shared File Storage For The Company Offices

## Lets try this exercise;
The company is geographically dispersed with offices in different locations. These offices need a way to share files and disseminate information. For example, the Finance department needs to confirm cost information for auditing and compliance. This file shares should be easy to access and load without delay. Some content should only be accessed from selected corporate virtual networks.
## Exercise Instructions
## Create And Configure A Storage Account For Azure Files.
1. Create a storage account for the finance department’s shared files.
- In the portal, search for and select Storage accounts.
- Select + Create.
- For Resource group select Create new. Give your resource group a name and select OK to save your changes.
- Provide a Storage account name. Ensure the name meets the naming requirements.
- Set the Performance to Premium.
- Set the Premium account type to File shares.
- Set the Redundancy to Zone-redundant storage.
- Select Review and then Create the storage account.
- Wait for the resource to deploy.
- Select Go to resource.
## Create And Configure A File Share With Directory.
1. Create a file share for the corporate office. 
- In the storage account, in the Data storage section, select the File shares blade.
- Select + File share and provide a Name.
- Review the other options, but take the defaults.
- Select Create
2. Add a directory to the file share for the finance department. For future testing, upload a file.
- Select your file share and select + Add directory.
- Name the new directory finance.
- Select Browse and then select the finance directory.
- Notice you can Add directory to further organize your file share.
- Upload a file of your choosing.
## Configure And Test Snapshots.
1. Similar to blob storage, you need to protect against accidental deletion of files. You decide to use snapshots.
- Select your file share.
- In the Operations section, select the Snapshots blade.
- Select + Add snapshot. The comment is optional. Select OK.
- Select your snapshot and verify your file directory and uploaded file are included.
2. Practice using snapshots to restore a file.
- Return to your file share.
- Browse to your file directory.
- Locate your uploaded file and in the Properties pane select Delete. Select Yes to confirm the deletion.
- Select the Snapshots blade and then select your snapshot.
- Navigate to the file you want to restore,
- Select the file and the select Restore.
- Provide a Restored file name.
- Verify your file directory has the restored file.
## Configure Restricting Storage Access To Selected Virtual Networks.
1. This tasks in this section require a virtual network with subnet. In a production environment these resources would already be created.
- Search for and select Virtual networks.
  - Select Create. Select your resource group. and give the virtual network a name.
  - Take the defaults for other parameters, select Review + create, and then Create.
  - Wait for the resource to deploy.
  - Select Go to resource.
- In the Settings section, select the Subnets blade.
  - Select the default subnet.
  - In the Service endpoints section choose Microsoft.Storage in the Services drop-down.
  - Do not make any other changes.
  - Be sure to Save your changes.
2. The storage account should only be accessed from the virtual network you just created.
- Return to your files storage account.
- In the Security + networking section, select the Networking blade.
  - Change the Public network access to Enabled from selected virtual networks and IP addresses.
  - In the Virtual networks section, select Add existing virtual network.
  - Select your virtual network and subnet, select Add.
  - Be sure to Save your changes.
- Select the Storage browser and navigate to your file share.
- Verify the message not authorized to perform this operation. You are not connecting from the virtual network.
