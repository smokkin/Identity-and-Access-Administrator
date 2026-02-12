Lab scenario
Your company works has Active Directory Domain Services on-premises. They would like to continue to use on-premises Active Directory as their identity and access management solution, but also require the ability for users to access cloud applications with the same username and password.

Estimated time: 60 minutes
Exercise 1 - Setup On-Premises infrastructure
Task 1 - Create the on-premises Active Directory infrastructure
Deployment template can be accessed at this link: https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.

Note to learners and MCTs - The deployment of this template can take 30-60 minutes, so be ready to take a break at this step or run the deployment before a lecture section of the course.

Note to Lab providers - If possible, it would be helpful to students to complete and deploy as part of the lab environment setup.

On the TLG (Test Lab Guide) - 3 VM Base Configuration (v1.0) page, select Deploy to Azure.

Note - The 3 VM Base Configuration provisions a Windows Server 2016 Active Directory domain controller named DC1 using the domain name you specify, and a domain member server named APP1 running Windows Server 2016. It also offers an option to provision a client VM running Windows 10, however we will not be using it in our lab (primarily due to licensing requirements applicable when running Windows 10 VMs in Azure). The domain member server (APP1) has automatically installed .NET 4.5 and IIS.

Note - The VM that is required for this lab is DC1.

On the Custom deployment page, specify the following settings, then select Review + Create then Create.

Subscription: The name of the target Azure subscription where you want to provision the lab environment Azure VMs.
Resource group: (Create new) hybrididentity-RG
Location: The name of the Azure region that will host the lab environment Azure VMs.
Config Name: TlgBaseConfig-01
Domain Name: corp.contoso.com
Server OS: 2016-Datacenter
Admin Username: demouser
Admin Password: Enter a secure password that you will remember
Deploy Client VM: No
Client VHD URI: leave blank
VM Size: Standard_D2s_v3
Note - Use a similar VM size if your subscription does not support the listed size. Documentation is linked here: https://docs.microsoft.com/en-us/azure/virtual-machines/windows/sizes.

DNS Label Prefix: Any valid, globally unique DNS name (a unique string consisting of letters, digits, and hyphens, starting with a letter and up to 47 characters long).

_artifacts Location: Accept the default

_artifacts Location Sas Token: leave blank

Select Review + Create.

After validation has passed, select Create.

Wait for the deployment to complete. This might take about 60 minutes.

