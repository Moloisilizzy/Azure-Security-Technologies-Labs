# Azure Security Technologies Labs
## Overview
This lab involved deploying and configuring Azure Firewall as a central security control for traffic moving between subnets in a virtual network. i worked through setting up network rules, application rules, and route tables integrations to enforce and monitor traffic flow with precision. i also upddated the original ARM template to align the deployment with the West Europe region, ensuring full compatibility and consistent resource provisioning. Overall, the exercise strenthned my understanding of how Azure Firewall delivers scalable, policy-driven protection across cloud enviroments
## Task 1: Using a template to deploy the lab enviroment
Signed in to the Azure Portal using the provided account details
Deployed lab resources using the provided template.json file 
Edited the template to change the region from East US to West Europe for cpmpatibility.
Deployment included:
1. Avirtual network with multiple subnets( including AzureFirewallSubnet)
2. Two virtual machines for testing (TestFW01 and SRV-Work267)
3. A route table and associated resources
