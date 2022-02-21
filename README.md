[![published](https://static.production.devnetcloud.com/codeexchange/assets/images/devnet-published.svg)](https://developer.cisco.com/codeexchange/github/repo/sandkum5/ucs_findCIMC)

# ucs_findCIMC
- Script to find UCS C-series Servers in a subnet
- Get UCS CIMC Product,Vendor Info using Redfish API without Auth

### Note: 
- This will only work with CIMC version 3.0 or higher which has Redfish API support.
- Redfish is enabled by default starting with CIMC version 4.0.4b. 
- To enable Redfish in prior versions, 
  - Login to CIMC
  - Go to Admin > Communication Services > Communication Services > Redfish Properties 
  - `Redfish Enabled` checkbox should be checked

### Pre-requisites
- PowerShell
  - For PowerShell installation, refer: [Install PowerShell](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell?view=powershell-7.2)

### How to Run
- Assign executable permissions to the findCIMC.ps1 file.
- To execute, run: ./findCIMC.ps1
- Enter a Subnet ID in format x.y.z. The subnet ID in which you want to search UCS C-series servers.
- Enter the Start IP and End IP in the subnet.
- UCS servers will return a Product Id and Company attributes and others won't.


`Sample Run:`

```
> ./findCIMC.ps1
Please enter the subnet id in format [198.19.216]: 198.19.216 
Please enter the start IP last octet [163]: 150
Please enter the end IP last octet [167]: 165
Target: 198.19.216.150, Not Reachable
Target: 198.19.216.151, Not a Cisco UCS Server: Status Code: 404
Target: 198.19.216.152, Not a Cisco UCS Server: Status Code: 404
Target: 198.19.216.153, Not a Cisco UCS Server: Status Code: 404
Target: 198.19.216.154, Not a Cisco UCS Server: Status Code: 500
Target: 198.19.216.155, Not a Cisco UCS Server: Status Code: 500
Target: 198.19.216.156, Not a Cisco UCS Server: Status Code: 500
Target: 198.19.216.157, Not a Cisco UCS Server: Status Code: 500
Target: 198.19.216.158, Not Reachable
Target: 198.19.216.159, Not Reachable
Target: 198.19.216.160, Not Reachable
Target: 198.19.216.161, Not Reachable
Target: 198.19.216.162, Product Id: UCSC-C220-M5SX, Company: Cisco Systems Inc.                                         
Target: 198.19.216.163, Product Id: UCSC-C220-M5SX, Company: Cisco Systems Inc.                                         
Target: 198.19.216.164, Product Id: UCSC-C220-M5SX, Company: Cisco Systems Inc.                                         
Target: 198.19.216.165, Product Id: UCSC-C220-M5SX, Company: Cisco Systems Inc.   
```
