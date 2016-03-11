# O365SilverStack
This Azure ARM template will deploy a load balanced fault tolerant IaaS for o365 servers, ADFS, WAP, ADDC, AAD Connect

v1 of this ARM one click deployment is the begining to get as much as possible to a zero or light touch deployment as possible for ADDC,ADFS,WAP,AADCONNET servers for Azure AD \ Office 365. The goal here to test drive Azure's superior IaaS offerings for a load balanced solution for directory sync and single sign on for your Azure AD \ Office 365 deployment. This should elminate time spent on setting up and designing this solution click and head to Lunch, return and the components are there and ready to be configured. Their will be further development on automation through ARM template and DSC for the servers in the next iteration.

Please send comments and suggestions to nate.swift@live.com





After Deployment:

From Azure (ARM Portal)

Set VNET for on premise AD DNS server
Connect VNET S2S to on premise network (Partial Future Automation)
Create NSG on Subnet 2 for Web Application Proxy servers(See Below Appendix A) (Future Automation)
Assign backenaddress pools for ADFSILB using AVset-ADFS and ADFS01,02 (Future Automation)
Assign backenaddress pools for PROXLB using AVset-PROX and PROX01,02 (Future Automation)


On Servers: (Partial Future Automation)

Install ADDS Role on ADDC01,02
Configure ADDC01,02 to add a domain forest to existing domain
Join ADFS01,02,SYN01 to domain
on DSYN01 Install and configure directory sync using Azure AD Connect
Install ADFS Role on ADFS01,02
Configure ADFS
Install WAP Role on ADFS01,02
Configure WAP

From Azure (ARM Portal)

Remove PIP1-7 addresses once S2S is up and hybrid connectivity established
Change VNET for Azure ADDC01,02 as AD DNS servers


Appendix A:

Create a .csv file for your NSG needs a sample and ps script can be found: https://onedrive.live.com/redir?resid=B3BD82E4293DFD9E!103296&authkey=!AA31KIYnaah-JME&ithint=folder%2ccsv 





