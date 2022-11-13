# Honeypot Assignment

**Time spent:** **5** hours spent in total

**Objective:** Create a honeynet using MHN-Admin. Present your findings as if you were requested to give a brief report of the current state of Internet security. Assume that your audience is a current employer who is questioning why the company should allocate anymore resources to the IT security team.

### MHN-Admin Deployment (Required)
<img width="554" alt="image" src="https://user-images.githubusercontent.com/112200901/201505009-ab3055d6-bcca-4d01-a4e4-0d9cc61608e2.png">

**Summary:** How did you deploy it? Did you use GCP, AWS, Azure, Vagrant, VirtualBox, etc.?

To deploy the MHN Admin I used Google Cloud Platform's free tier and provisioned the VM. I made the VM accessible to me via SSH and made sure it had an internet facing IP. Other attributes were also provisioned including Ubuntu 18.04 Minimal, HTTP traffic allowed (port 80), and TCP ports 3000 and 10000 need to be open to allow incoming traffic for geolocation and honeypot sensor data. I also configured specific firewall rules such as: 

gcloud compute firewall-rules list

gcloud compute firewall-rules create http ^
    --allow tcp:80 ^
    --description="Allow HTTP from Anywhere" ^
    --direction ingress ^
    --target-tags="mhn-admin"

gcloud compute firewall-rules create honeymap ^
    --allow tcp:3000 ^
    --description="Allow HoneyMap Feature from Anywhere" ^
    --direction ingress ^
    --target-tags="mhn-admin"

gcloud compute firewall-rules create hpfeeds ^
    --allow tcp:10000 ^
    --description="Allow HPFeeds from Anywhere" ^
    --direction ingress ^
    --target-tags="mhn-admin"


After that, I created the MHN-Admin VM itself using:

gcloud compute instances create "mhn-admin" ^
    --machine-type "n1-standard-1" ^
    --subnet "default" ^
    --maintenance-policy "MIGRATE" ^
    --tags "mhn-admin" ^
    --image-family "ubuntu-minimal-1804-lts" ^
    --image-project "ubuntu-os-cloud" ^
    --boot-disk-size "10" ^
    --boot-disk-type "pd-standard" ^
    --boot-disk-device-name "mhn-admin"
    <img width="805" alt="image" src="https://user-images.githubusercontent.com/112200901/201505612-ea627c64-038b-47b7-b57c-2227279df5a4.png">
<img width="731" alt="image" src="https://user-images.githubusercontent.com/112200901/201505629-94eb89b7-c52d-4350-8e55-3ea75f2652c0.png">

    <img src="mhn-admin.gif">
### Dionaea Honeypot Deployment (Required)

**Summary:** Briefly in your own words, what does dionaea do?

Dionaea emulates SSH and telnet services, the honeypot captures malware and detects shellcode. The goal is to gain information about the different malware, so it logs the actions taken by attackers. 

<img width="952" alt="image" src="https://user-images.githubusercontent.com/112200901/201506041-feb98426-1725-42b8-9326-99e031474a4d.png">

<img width="960" alt="image" src="https://user-images.githubusercontent.com/112200901/201506051-0f871213-34fb-4267-b5af-305b840be64d.png">

<img src="dionaea-honeypot.gif">

### Database Backup (Required) 

**Summary:** What is the RDBMS that MHN-Admin uses? What information does the exported JSON file record?

The RDBMS that MHN-Admin uses is Ubuntu. The exported JSON file records a copy of the attacks that were made on the honeypot. It contains information such as the honeypot they attacked, the session ID, the port, date and time, location, and more.

![sessionjson1](https://user-images.githubusercontent.com/112200901/201506660-0bd7cf73-1236-492e-a69b-8090298e44d6.gif)


*Be sure to upload session.json directly to this GitHub repo/branch in order to get full credit.*



## Notes

Describe any challenges encountered while doing the assignment.

A challenge was my internet connection, some steps took a while to execute. 
