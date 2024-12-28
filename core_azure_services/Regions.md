## Regions for virtual machines in Azure
[Regions for virtual machines in Azure](https://learn.microsoft.com/en-us/azure/virtual-machines/regions?wt.mc_id=searchAPI_azureportal_inproduct_rmskilling&sessionId=4ec4546e831e4bf782973c7c0c388926)

To check Azure regions in your Azure environment, you can use several methods depending on your preference for using the Azure portal, command-line tools, or programming interfaces:

1. Azure Portal
Log in to the Azure Portal.
Go to the "Regions" page:
Click on "Help + Support" in the navigation menu.
Under "Service Information", select "Regions".
The Regions page will display all the available Azure regions, including their status and location.
2. Azure CLI
You can use the Azure CLI to list all available regions for your subscription. Run the following command:

bash
Copy code
az account list-locations -o table
This will display a table of all available Azure regions, including their names and display names.

3. Azure PowerShell
Use the Azure PowerShell module to retrieve available regions:

powershell
Copy code
Get-AzLocation | Select-Object Location, DisplayName
This command will list all regions and their display names for your Azure subscription.

4. REST API
Azure's REST API allows you to fetch the list of available locations programmatically. Make a GET request to the following endpoint:

bash
Copy code
GET https://management.azure.com/subscriptions/{subscriptionId}/locations?api-version=2020-01-01
Replace {subscriptionId} with your subscription ID. Ensure that you authenticate with an appropriate token.

5. Azure SDK
If you're working with Azure SDKs (e.g., Python, .NET), you can use the SDK to programmatically retrieve region information.

Example in Python:
python
Copy code
from azure.identity import DefaultAzureCredential
from azure.mgmt.resource import SubscriptionClient

credential = DefaultAzureCredential()
subscription_client = SubscriptionClient(credential)

subscription_id = "your-subscription-id"
locations = subscription_client.subscriptions.list_locations(subscription_id)

for location in locations:
    print(location.name, location.display_name)
6. Azure Regions Website
Visit the official Azure website's Regions page:

[Azure Global Infrastructure](https://azure.microsoft.com/en-us/explore/global-infrastructure/geographies/)
This page provides an overview of all Azure regions, their locations, and services available in each region.