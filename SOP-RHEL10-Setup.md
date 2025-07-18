<br>
<br>
<br>
<br>
<br>
<br>
<br>
<div align="center">
  <h1>Standard Operating Procedure for New VM Creation on RHEL 10</h1>
  Manitoba Institute of Trades and Technology  <br>
  130 Henlow Bay, Winnipeg, MB R3Y 1G4  <br>
  2049896500  <br>
</div>

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

**Reversion info:**  <br>
| Version	| Date	| Author |	Description of Change |
|---------|-------|--------|------------------------|
| 1.0	| 2025-07-18	| TiantianLi	| Initial document creation. |

**Approved Table:**  <br>
| Role	| Name	| Signature	| Date |
|-------|-------|-----------|------|
|Author |	TiantianLi	|	    |2025-07-18|
|Reviewer	|           |		  |          |
|Approver	|           |     |          |

## PURPOSE
The purpose of this Standard Operating Procedure (SOP) is to provide clear, step-by-step instructions for setting up a Red Hat Enterprise Linux (RHEL) 10 virtual machine. This procedure ensures that all test environments are created with consistent configurations, which supports reliable application testing and reduces setup errors.

## SCOPE
This document applies to all IT personnel, including system administrators and QA engineers, who are responsible for creating testing environments. The scope covers the entire process, from initial planning and VM configuration in VMware Workstation to the installation of the operating system, deployment of the necessary software stack, and final verification. The detailed objective is to produce a fully functional RHEL 10 server ready for web application testing.

## ACCOUNTABILITY MATRIX  
| **Task Area** |	**Responsible** | **Review/Approval** |
|----------------|----------------|-------------------------------|
| Planning and Resource Assessment	| System Administrator          |
| Virtual Machine Creation & Configuration	| IT Support  Team|
| OS and Application Stack Installation |	System Administrator |
| Verification and Functional Testing |	Quality Assurance Team |
| Final Documentation |	Author / System Administrator |

## DEFINITIONS
- **SOP:** Standard Operating Procedure. A document that provides step-by-step instructions to help workers carry out complex routine operations.  
- **VM:** Virtual Machine. A software-based computer that runs on a physical host server.  
- **RHEL:** Red Hat Enterprise Linux. A popular, enterprise-grade Linux operating system.
- **VMware Workstation:** A desktop hypervisor application that allows users to run multiple operating systems as virtual machines on a single physical computer.
- **LEMP:** An acronym for a popular software stack used for web development, consisting of Linux, Nginx (Engine-X), MySQL/MariaDB, and PHP.  
- **VMware Tools:** A suite of utilities that enhances the performance and management of a virtual machine.   

## PROCEDURE STEPS
The following steps describe the complete procedure for creating and configuring the RHEL 10 virtual machine using VMware Workstation.
### Step 1: Planning and VM Creation in VMware Workstation
#### Step 1.1: Plan Resources  
Before starting, confirm the VM requirements:
  - **CPU:** 2 vCPUs  
  - **RAM:** 2 GB  
  - **Disk Space:** 30 GB  
  - Ensure a Red Hat subscription is available for system registration.
#### Step 1.2: Create New VM
Launch VMware Workstation and start the "New Virtual Machine" wizard. Select "Custom (advanced)" for more control.  
#### Step 1.3: Configure VM:  
Proceed through the wizard with the following settings:  
- **Guest Operating System:** Select Linux, and for the version, choose Red Hat Enterprise Linux 9 (64-bit).
- **Virtual Machine Name:** rhel9-webapp-test.
- **Processor Configuration:** Assign 2 processors.
- **Memory:** Assign 2048 MB (2 GB).
- **Network Type:** Select Use bridged networking.
- **Disk:** Create a new virtual disk and allocate 30 GB of space. Store it as a single file for better performance.
#### Step 1.4:Attach ISO:  
Before finishing the wizard or in the VM settings afterward, configure the virtual CD/DVD drive to use the rhel-10.x-x86_64-dvd.iso image file.

### Step 2: RHEL 10 Operating System Installation
#### Step 2.1: Start Installation
Power on the newly created virtual machine to boot from the ISO image.
#### Step 2.2: Configure Installation
On the "Installation Summary" screen, configure the following:  
- **Network & Host Name:** Enable the network adapter. Configure：  
    - **IPv4 address：** 192.168.1.101  
    - **netmask：** 255.255.255.0  
    - **gateway：** 192.168.1.1
    - **DNS：** 8.8.8.8.
- **Software Selection:** Choose Minimal Install as the Base Environment.
- **User Settings:** Set a strong password for the root user and create a standard administrator user.
#### Step 2.3: ystem Configuration and Software Installation 
- **Connect and Register:** Log in to the server via SSH (ssh your_username@192.168.1.101). Register the system with Red Hat: 

   `sudo subscription-manager register --username YOUR_RHN_USERNAME --password YOUR_RHN_PASSWORD --auto-attach`  

- **Update System:** Run a full system update to ensure all packages are current.

   `sudo dnf update -y`  

- **Install VMware Tools:** Install the open-source version of VMware Tools for improved performance and integration.  

   `sudo dnf install -y open-vm-tools`

   **Note:** This step is crucial for features like proper screen resolution, copy-paste, and performance monitoring within VMware Workstation.

- **Install LEMP Stack:** Install the web server, database, and PHP components.

   `sudo dnf install nginx mariadb-server php-fpm php-mysqlnd -y`  

- **Enable and Secure Services:** Enable the services to start on boot and then secure the database.

   `sudo systemctl enable --now nginx`  
   `sudo systemctl enable --now mariadb`  
   `sudo mysql_secure_installation`  




### Step 4: Firewall and Final Verification
#### Step 4.1: Configure Firewall
Allow HTTP and HTTPS traffic through the system's firewall.  

   `sudo firewall-cmd --permanent --add-service=http`  
   `sudo firewall-cmd --permanent --add-service=https`  
   `sudo firewall-cmd --reload`  

#### Step 4.2: Test Environment
Create a temporary test file to verify that the web server can process PHP files.  

   `echo "<?php phpinfo(); ?>" | sudo tee /usr/share/nginx/html/info.php`  

#### Step 4.3: Verify in Browser
- Open a web browser and navigate to http://192.168.1.101/info.php.  
- A successful test will display the PHP information page.  
#### Step 4.4: Cleanup
For security purposes, remove the test file after verification.  
 
   `sudo rm /usr/share/nginx/html/info.php`  

### Step 5: Documentation
#### Step 5.1: Record Details
Document all important details of this VM (IP address, credentials, software versions) in the company's central knowledge base.
#### Step 5.2: Notify Team
Inform the relevant teams that the new test environment is ready and provide them with the necessary access information.
## Reference or Related Documents
- Red Hat Enterprise Linux 9 Official Documentation:  
   https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/9
- VMware Workstation Pro Documentation:  
   https://docs.vmware.com/en/VMware-Workstation-Pro/index.html
- Nginx Documentation:  
   https://nginx.org/en/docs/
