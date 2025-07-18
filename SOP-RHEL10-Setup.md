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

## PURPOSE
This document outlines the standardized procedures for creating new virtual machines with Red Hat Enterprise Linux (RHEL) 10. Its purpose is to ensure consistency, proper configurations, and adherence to best practices during the setup of a web application testing environment.
## AUDIENCE
This guide is for people in the IT team, System Administrators, and the QA team. It is for anyone who needs to make a new VM for testing web applications.
## APPROVAL TABLE
| Version | 	 Date   |                  Name                     |	  Designation    |
|---------|-----------|-------------------------------------------|------------------|
|   1.0   | yy-mm-dd  |	TiantianLi (tiantianli1@student.mitt.ca)	|      Author      |
|   1.0	  | yy-mm-dd	|                                           |      Reviewer    |
|   1.0	  | yy-mm-dd	|             	                            |      Approver    |
## SCOPE/OBJECTIVES
This guide explains all the steps to set up a RHEL 10 VM for testing. The main goals are:

1.To plan before we make the VM.  
2.To set up the VM's hardware correctly.  
3.To install the RHEL 10 operating system.  
4.To install the web server software (LEMP).  
5.To check that the new VM works.  
6.To write down all the details about the VM.  

## ACCOUNTABILITY MATRIX
| Task/Steps	 | Responsible Person/Team	| Contact	| Review/Approval |
|--------------|--------------------------|---------|-----------------|
| Pre-creation Planning & Assessment|System Administrator	| Email/Distribution List	| IT Manager |
|Configuration of Virtual Machine |	IT Team	| Email/Distribution List	| IT Ops Manager |
|Installation of Guest OS & LEMP Stack	| System Administrator |	Email/Distribution List	| QA Manager |
|Post-creation Verification & Testing	| Quality Assurance Team	| Email/Distribution List	| QA Manager |
|Documentation of Virtual Machine	| Author (SysAdmin)	| Email/Distribution List	| Author|
## EXECUTION STEPS
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
