# Ancora-Education-Ucertify-Lab31
# Configuring Syslog and Viewing Settings on a Router

Syslog is a protocol that is used to send log messages over a network. It is commonly used by devices such as routers, switches, and firewalls to log system events. Viewing the settings on a router can be done by logging into the router's web-based interface or by using a command line interface (CLI).

> **Original Lab Source**
> 
> This lab was available through:
>
> [https://ancoraeducation.ucertify.com/app/?func=navigate_items&item_sequence=4]

## Instructions
The PuTTY SSH Client is used in this lab. It is a popular SSH and Telnet Client that provides a secure way to access remote systems. You are provided with the Linux virtual machine.

**Topology**

Topology refers to the arrangement or configuration of the virtual network connections within the virtual machine (VM) environment. It defines how the virtual network interfaces and components are interconnected and organized
## Objective of the Lab
This lab session demonstrates the steps involved in configuring Syslog and viewing settings on a router. Upon completion of this lab, you will be able to: 
* Understand the concept of Syslog and its importance in network administration. *
* Configure Syslog on a router.
* View and modify settings on a router.
## PART A: Establishing the Telnet Connection
### Caution
If the virtual machine gets restarted automatically during the task, then please Reset the machine and perform the task again. 

Access the PuTTY console with IP address as 192.168.116.128, Port as 5003, and Connection type as Other.
### STEP 1
From the left sidebar, open PuTTY SSH Client. The PuTTY Configuration dialog box will appear on the screen.
### STEP 2
Type Host Name (or IP address) as 192.168.116.128
###  STEP 3
Type Port as 5003
### STEP 4
Select the Other radio button.
### STEP 5
Click Open to connect the R8 terminal window.
### STEP 6
If you don't get a command line prompt in the terminal window, then press Enter.
## PART B: Configuring Syslog and Observing the Log Settings
Enter into configuration mode and execute the commands to configure Syslog, logs messages to the 192.168.2.100 host, and observe the configured log settings.
### STEP 1
Execute the following commands to enter into configuration mode and configure Syslog (Note: Execute one command at a time.):
```bash
configure terminal
```
```bash
logging console 7
```
```bash
logging monitor debug
```
```bash
logging buffered 4
```
```bash
logging host 192.168.2.100
```
```bash
logging trap warning
```
```bash
end
```
### NOTE
* The configure terminal command allows you to enter global mode/configuration commands.
* The logging console 7 command causes IOS to send severity level 0–7 messages to the console.
* The logging monitor debug command limits messages logged to the terminal lines.
* The logging buffered 4 command logs messages to an internal buffer. The default buffer size is 4096.
* The logging host 192.168.2.100 command logs messages to a UNIX Syslog server host.
* The logging trap warning command limits messages logged to the Syslog servers.
### STEP 2
Execute the following command to display the state of system logging (Syslog) and the contents of the standard system logging buffer:
```bash
show logging
```
### CAUTION
If you see --More--, keep pressing Enter until you see the command line prompt, ending with a hash symbol (#). 
### STEP 3 
Close all windows. At the PuTTY Exit Confirmation prompt, click Yes. 
### Lab Summary 
This lab session provides you with a straightforward and practical understanding of Syslog and how to configure and view settings on a router. Here's a summary of what you have learned: 
* How to configure Syslog on a router, allowing the router to send log messages to a centralized Syslog server.
*  How to view and modify settings on a router, ensuring that the router is correctly configured.
*  How to test Syslog functionality by sending log messages to a Syslog server.

Now, you are equipped with the knowledge and skills to configure Syslog and view settings on a router effectively.

## Disclaimer

This repository is for **educational and personal learning purposes only**.  

The original lab content belongs to **uCertify / Ancora Education** and remains their copyrighted material. This repository is not affiliated with, endorsed by, or sponsored by uCertify or Ancora Education.  

No copyright infringement is intended.  
Use of any tools or techniques mentioned here should only be performed in authorized, legal environments.
