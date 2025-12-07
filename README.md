# Azure Security Technologies Labs
## Overview
This lab involved deploying and configuring Azure Firewall as a central security control for traffic moving between subnets in a virtual network. i worked through setting up network rules, application rules, and route tables integrations to enforce and monitor traffic flow with precision. i also upddated the original ARM template to align the deployment with the West Europe region, ensuring full compatibility and consistent resource provisioning. Overall, the exercise strenthned my understanding of how Azure Firewall delivers scalable, policy-driven protection across cloud enviroments
## Task 1: Using a template to deploy the lab enviroment
Deployed lab resources using the provided template.json, updating the region to East US. Setup included a virtual network with subnets, two sets VMs(Test-FW01 and SRV-Work267), and a route table.
![task 1 screenshoot](azure%20firewall%20images/task%201.png)
![TASK1 Tscreenshoot](azure%20firewall%20images/TASK1_T.png)
## Task 2: Deploy an Azure Firewall
I deployed the Azure Firewall in the virtual network from Task 1. I used the Azure Portal to create the firewall with the provided settings, then verified the deployment by checking the AZ500LAB08 resource group and identifying the private IP address assigned to Test-FW01.
![task 2A screenshoot](azure%20firewall%20images/task%202A.png)
![TASK 2 screenshoot](azure%20firewall%20images/TASK%202.png)
## Task 3: Created a default route
I created a default route for the Workload-SN subnet to route outbound traffic throuth the Azure Firewall. I set up a new roye table, completed the deployment, and configured Firewall-Route entry to ensure all traffic passes through the firewall
![TASK 3 screenshoot](azure%20firewall%20images/TASK%203.png)
## Task 4: Configure an application rule
I created an application rule on the Test-FW01 firewall to allow outbound access to www.bing.com. I navigated to the firewall's Rules(Classic) section, added a new application rule collection, specifiedthe required settings, and created a target entry for the FQDN to enable the desired outbound access.
![TASK 4 screenshoot](azure%20firewall%20images/TASK%204.png)
## Task 5: Configure a network rule
The network rule collection controlled outbound network access based on IP address and port configuration
![TASK 5 screenshoot](azure%20firewall%20images/TASK%205.png)
## Task 6: Configure the virtual machine DNS server
Navigated to AZ500LAB08, selected the SRV-Work virtual machine, opened Networking -> Network Interface, set DNS servers to Custom, added 209.244.0.3 and 209.244.0.4, saved, and waited for the update to complete.
![TASK 6 screenshoot](azure%20firewall%20images/TASK%206.png)
## Task 7:Testing the firewall
Two virtual machines (Test-FW01 and SRV-Work267) were deployed and accessed via RDP to validate outbound accessn and forewall rules. Testing confirmed allowed sites were reachable(e.g Bing), while Blocled sites(Microsoft) were inaccessible, showing the firewall worked as intended.
![task 1 screenshoot](azure%20firewall%20images/task%201.png)
## Clean upresources
The resource group AZ500LAB08 was deleted using PoweShell:
Remove-AZResourceGroup -Name "AZ500LAB08" -Force -A
![task 7 screenshoot](azure%20firewall%20images/task%207.png)

## Summary
This lab demonstrated deploying Azure Firewall to enforce centralized network security. By integrating it with route tables, DNS, and rule collections, consistent policies were aplied across subnets. Using an ARM template enabled automated and repeatable deployment of a secure Azure enviroment.
