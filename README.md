
# WannaCry Malware Analysis Lab

This project provides an in-depth analysis of the WannaCry executable using a combination of static and dynamic analysis techniques. The analysis was conducted in a controlled environment using virtualization tools and various malware analysis tools.

## Objective

The primary goal of this project is to understand the behavior and functionality of the WannaCry malware through both static and dynamic analysis methods. The analysis was performed in a controlled environment to ensure the safety of the host system.

## Tools Used

- **VirtualBox** 

- **REMnux** 

- **FlareVM**

- **PEStudio**

- **Procmon** 

- **Ghidra** 

- **Wireshark** 

## **Setting up the Enviroment**
   - Created a virtual machine using VirtualBox to isolate the malware from the host system.
   - Utilized FlareVM and REMnux as dedicated analysis environments for Windows and Linux-based analysis tools.
   - FlareVM will be the primary isolated VM worked in, REMnux is used for WireShark analysis in this lab.
## Analysis Proccess

### **Static Analysis with PEStudio**

   - Ran the WannaCry executable through PEStudio to gather information about its imports, exports, resources, and potential indicators of compromise (IOCs).
   - Analyzed the file's structure, libraries, and suspicious characteristics.
   - Note the execuable's header for any suspicous API calls or suspicous hex values

### **Dynamic Analysis with Procmon**

   - Executed the WannaCry executable in a controlled environment with Procmon running to capture system-level events.
   - Monitored file system changes, registry modifications, network connections, and process creation events.

### **Binary Analysis with Ghidra**

   - Loaded the WannaCry binary into Ghidra to decompile and analyze the malware's code.
   - Identified key functions, API calls, and potential vulnerabilities in the code.
   - Examined the malware's behavior and functionalities revealed through static analysis.

### **Network Analysis with Wireshark**

   - Captured network traffic while the malware was executing using Wireshark.
   - Analyzed the communication patterns, protocols used, and any identifiable patterns in the network traffic.

## Conclusive Analysis
The WannaCry malware is classified as ransomware, intially spreading through Microsoft's system EternalBlue
Once inside the network the WannaCry software moves laterally across the network through the SMB protocol
WannaCry then encrypts files across the host such as images,documents and databases
Then a ransomware note displays on the host screen, demaning payment as Bitcoin for the encyption key
The malicious software also has a killswitch, meaning if the program can/can not reach a specific domain it stops spreading through the network
