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
sfdx auth:web:login --setdefaultdevhubusername --setalias DevHubYourBrand
sfdx auth web login -d -a DevHubYourBrand
```
## 5. Make project-scratch-def.json
```
{
  "orgName": "LPS Internal CRM",
  "country": "HK",
  "language": "En",
  "adminEmail": "o.mh.liu@pccw.com",
  "username": "lps-dev-01@pccw.com",
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
## 6. make scratch org 
```
sfdx org create scratch -a dev01 -y 30 -f config/project-scratch-def.json
```

## 7. generate password and change password
```
sfdx force user password generate -u dev01
```

## 8. check org info 
```
sfdx org list --all
sfdx org display --target-org stage
```

The example result:
```
=== Org Description

 KEY             VALUE                                                                                                  
 ─────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────── 
 Access Token    00D0p0000001pbQ!AQoAQO.7QuoqyTpaxn19RYIKvjM0AWzhfTcaC0FxNtOkzlHCA3SseWmcat9wJnVWHfDNtVvYm_NqqT6vv_Bao… 
 Alias           stage                                                                                                  
 Client Id       PlatformCLI                                                                                            
 Created By      oscar.m.liu@mindful-moose-tip0lh.com                                                                   
 Created Date    2023-02-19T05:47:44.000+0000                                                                           
 Dev Hub Id      oscar.m.liu@mindful-moose-tip0lh.com                                                                   
 Edition         Developer                                                                                              
 Expiration Date 2023-03-21                                                                                             
 Id              00D0p0000001pbQEAQ                                                                                     
 Instance Url    https://drive-momentum-797-dev-ed.scratch.my.salesforce.com                                            
 Org Name        Scratch Org 1                                                                                          
 Password        mjvtbhC5tn(vl                                                                                          
 Signup Username test-pccwdemo-xxxx@sample.com                                                                          
 Status          Active                                                                                                 
 Username        test-pccwdemo-xxxx@sample.com

```

