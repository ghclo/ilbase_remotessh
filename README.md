# ilbase_remotessh

https://github.com/Azure/azure-cli-extensions/issues/550
This repo just saves the modified files so I can curl them down in the vm in ilb ase

The current version of Azure CLI 2.0.62 does not support open SSH from remote shell to Linux App Service inside the Linux ILB ASE v2 because ILB ASE Kudu requires to input publish credentail.

"In the multitenant App Service and in an External ASE, there's single sign-on between the Azure portal and the Kudu console. For the ILB ASE, however, you need to use your publishing credentials to sign into the Kudu console."
https://docs.microsoft.com/en-us/azure/app-service/environment/create-ilb-ase#publish-with-an-ilb-ase

Workaround: 
modify the custom.py and tunnel.py with the to remove the SSL check and replace the hardcoded scm url (scm.azurewebiste.net) to the ILB ASE scm domain.
