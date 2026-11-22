# hyperv-nested-vnet-peering
This Project is to set up Connectivity Between Hyper-V host and nested VM on it and Azure Hub vnet . it used Hub and Spoke Model of connectivity .
Vnet hosting Azure VM Hyper-V host and Azure Hub Vnet will have connectivity with vNet peering. 
Azure Hyper-V host will be provisioned with public IP address to provide outbound internet connectivity  .
Nested VM inside Hyper-V host will have Default Gateway as Azure Hyper-V host as its Default gateway.it will forward traffic to Hyper-V host in Azure VM
Azure VM hyper-V host will have native Azure vNet connectivity and it one of its interface will be connected to Hyper-V internal switch 
IP forwarding will be enabled on NIC Interface inside windows OS which connects to Azure vNet and Actual NIC interface on portal.
Any traffic destinated outbound from nested Guest OS to Azure will be forwarded to Hyper-V VM Azure NIC interface and it will routed outside via Azure NIC interface which has internet connectivity and hub vnet connectivity to connect other AZure VM resources
UDR will be created to route traffic back from Azure hub vnet to nested VM subnet with Azure Hyper-V host VM as next hop.
