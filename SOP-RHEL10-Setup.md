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

Reversion info:  <br>
| Version	| Date	| Author |	Description of Change |
|---------|-------|--------|------------------------|
| 1.0	| 2025-07-18	| TiantianLi	| Initial document creation. |

Approved Table:  <br>
| Role	| Name	| Signature	| Date |
|-------|-------|-----------|------|
|Author |	TiantianLi	|	    |2025-07-18|
|Reviewer	|           |		  |          |
|Approver	|           |     |          |

## PURPOSE
The purpose of this Standard Operating Procedure (SOP) is to provide clear, step-by-step instructions for setting up a Red Hat Enterprise Linux (RHEL) 10 virtual machine. This procedure ensures that all test environments are created with consistent configurations, which supports reliable application testing and reduces setup errors.

## SCOPE
This document applies to all IT personnel, including system administrators and QA engineers, who are responsible for creating testing environments. The scope covers the entire process, from initial planning and VM configuration to the installation of the operating system, deployment of the necessary software stack, and final verification. The detailed objectives to be achieved through this SOP are: a fully functional RHEL 10 server with a LEMP stack, configured with basic security measures, and ready for web application deployment.

## ACCOUNTABILITY MATRIX  
| **Task Area** |	**Responsible** | **Stockholder (Person/Team)** |
|----------------|----------------|-------------------------------|
| Planning and Resource Assessment	| System Administrator          |
| Virtual Machine Creation & Configuration	| IT Support / Virtualization Team|
| OS and Application Stack Installation |	System Administrator |
| Verification and Functional Testing |	Quality Assurance (QA) Team |
| Final Documentation |	Author / System Administrator |

## DEFINITIONS
- **SOP:** Standard Operating Procedure. A document that provides step-by-step instructions to help workers carry out complex routine operations.  
- **VM:** Virtual Machine. A software-based computer that runs on a physical host server.  
- **RHEL:** Red Hat Enterprise Linux. A popular, enterprise-grade Linux operating system.  
- **LEMP:** An acronym for a popular software stack used for web development, consisting of Linux, Nginx (Engine-X), MySQL/MariaDB, and PHP.  
- **SSH:** Secure Shell. A network protocol used for secure remote login and command execution on a server.   

## PROCEDURE STEPS
The following steps describe the complete procedure for creating and configuring the RHEL 9 virtual machine. Any known difficulties are mentioned within the relevant steps.
### Step 1: Pre-creation Planning and Assessment
#### Step 1.1: Identify Purpose and Requirements
We will use this VM to test our company's web applications.
#### Step 1.2: Define Resource Requirements
- Define resource requirements:  
  - **CPU:** 2 Cores  
  - **RAM (Memory):** 2 GB  
  - **Disk Space:** 30 GB  
  - **Network:** Bridged Mode with a static IP address.
### Step 2: Configuration of Virtual Machine
#### Step 2.1: Create a New Virtual Machine
#### Step 2.2: Configure Virtual Machine Settings
### Step 3: Installation of Guest OS and Application Stack
#### Step 3.1: Attach Installation ISO
#### Step 3.2: Install Guest OS
#### Step 3.3: System Registration and Updates
#### Step 3.4: Install LEMP Stack
### Step 4: Post-creation Verification and Testing
#### Step 4.1: Configure Firewall
#### Step 4.2: Functional Testing
#### Step 4.3: Security Compliance
### Step 5: Documentation of Virtual Machine
#### Step 5.1: Document Virtual Machine Details
#### Step 5.2: Knowledge Transfer
## REVISION HISTORY
