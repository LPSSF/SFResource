# Make Scratch Org for DevOps work item

The sfdx script makes a devops environment
If not the first time, please jump to Step 5, and please change the number in project-scratch-def.json

Plase backup the definition file and the data import file for future use. 

## 1. Install the CLI from https://developer.salesforce.com/tools/sfdxcli

## 2. update sfdx
```
sfdx update
```

## 3. create a playground from salesforce, open setting of dev hub. 

## 4. Set DevHub
```
sfdx auth web login -d -a pccwdevops

```
## 5. Make project-scratch-def.json
```
{
  "orgName": "LPS Internal CRM",
  "country": "HK",
  "language": "En",
  "adminEmail": "o.mh.liu@gmail.com",
  "username": "lps-dev-03@pccw.com",
  "edition": "Developer",
  "features": ["EnableSetPasswordInApi"],
  "settings": {
    "lightningExperienceSettings": {
      "enableS1DesktopEnabled": true
    },
    "mobileSettings": {
      "enableS1EncryptedStoragePref2": false
    }
  }
}

```
## 6. make scratch org , you need auth a devhub firstly before execute the below command 
```
sfdx org create scratch -a dev03 -y 30 -f config/project-scratch-def.json
```

## 7. generate password and change password
```
sfdx force user password generate -u dev03
```

## 8. check org info 
```
sfdx org list --all
sfdx org display --target-org dev03

```

The exampleKEY             VALUE                                                                                                            
 ─────────────── ──────────────────────────────────────────────────────────────────────────────────────────────────────────────── 
 Access Token    00D0l000000H4Xe!AQ0AQH2KOOpqELjiju5xnmkcgBOKgU3hlaALHUVu70Krm7ySI9YH_BBW.OS5h5Uoruqnq7830rZ9xcIhECALvU2ore1X9qht 
 Alias           dev03                                                                                                            
 Api Version     57.0                                                                                                             
 Client Id       PlatformCLI                                                                                                      
 Created By      system.devops@pccw.com                                                                                           
 Created Date    2023-04-25T07:48:05.000+0000                                                                                     
 Dev Hub Id      system.devops@pccw.com                                                                                           
 Edition         Developer                                                                                                        
 Expiration Date 2023-05-25                                                                                                       
 Id              00D0l000000H4XeEAK                                                                                               
 Instance Url    https://efficiency-drive-7494-dev-ed.scratch.my.salesforce.com                                                   
 Org Name        LPS Internal CRM                                                                                                 
 Password        Ejbw7zrv&qjtz                                                                                                    
 Signup Username lps-dev-03@pccw.com                                                                                              
 Status          Active                                                                                                           
 Username        lps-dev-03@pccw.com      



```

