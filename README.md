# 🛡️ ALSO Microsoft Security iOS and iPadOS Policy Templates

> Collection of Microsoft Security policy templates for iOS and iPadOS devices, covering both BYOD (Bring Your Own Device) and corporate-managed deployments. Includes automated onboarding to Microsoft Defender, App Protection Policies (MAM), App Configuration Policies, Compliance Policies, and Device Configuration Profiles to help organizations secure mobile devices while maintaining a productive user experience..

**Works with Business Premium and up.**

---

> [!IMPORTANT]
> **⚠️ IMPORTANT: Read this before importing and using any policies.**  

| Resource | Description |
|-----------|-------------|
| 🛡️ **Security Information** | [View Security Policy](https://github.com/CoC-MS/ALSO-Microsoft-Security-MacOS/tree/main?tab=security-ov-file) |
| 📖 **ALSO_IOS_MDE_AUTO_ONBOARDING Description** | [View description](https://github.com/CoC-MS/ALSO-Microsoft-Security-iOS#whats-included-in-also_ios_mde_auto_onboarding)
| 📖 **ALSO_IOS_APP_PROTECTION_POLICY Description** | [View description](https://github.com/CoC-MS/ALSO-Microsoft-Security-iOSandiPadOS#whats-included-in-also_ios_app_protection_policies)
| 📖 **ALSO_IOS_COMPLIANCE_POLICIES Description** | [View description](https://github.com/CoC-MS/ALSO-Microsoft-Security-iOSandiPadOS#whats-included-in-also_ios_compliance_policies)
| 📖 **ALSO_IOS_CA_POLICIES Description** | [View description](https://github.com/CoC-MS/ALSO-Microsoft-Security-iOSandiPadOS#whats-included-in-also_ios_compliance_policies)
| 🚀 **Before Importing ALSO_IOS_MDE_AUTO_ONBOARDING** | [Read Before Importing Policies](https://github.com/CoC-MS/ALSO-Microsoft-Security-iOS#before-importing-also_ios_mde_auto_onboarding) |


---

## 📂 File Structure

All files are organized into categories

```text
/ALSO-Microsoft-Security-MacOS

├── ALSO_IOS_MDE_AUTO_ONBOARDING/
|── Applications 1 application
|── DeviceConfiguration 1 Device Configuration policy templates
|── AppConfigurationManagedDevice 1 App Configuration policy template

├──ALSO_IOS_APP_PROTECTION_POLICIES/AppPro
|── AppPro 1 App Protection policy template

├──ALSO_IOS_APP_COMPLIANCE_POLICIES/CompliancePolicies'
|── CompliancePolicies 4 App Compliance policy templates

├──ALSO_IOS_CA_POLICIES/ConiditionalAccess
|── ConditionalAccess 3 Conditional Access policies
|── Groups 3 Conditional groups
|── MigrationTable.json


```

### License Tag Description

| Tag | Minimum Required License |
|:---:|--------------------------|
| **BP** | Microsoft 365 Business Premium |

---

## 📖 Naming Convention

All policy templates follow the naming format below:

```text
<ALSO>-<ImpactLevel>-<MinimumLicense>-<BaselineLevel>-<Version>-<OS>-<Main Category>-<Sub Category>-<Settings>-<Assignment>
```

### Example

```text
ALSO – LI – BP – Basic – v1.0– iOS/iPadOS BYOD or Corp –
```

---

## 🧩 Naming Components

| Component | Description |
|-----------|-------------|
| **ALSO** | Company providing the policy template to have a better control |
| **Impact** | Impact level of policy, low (LI), medium (MI) or high (HI) |
| **MinimumLicense** | Minimum Microsoft license required to use the policy |
| **BaselineLevel** | Baseline level of policy, Basic, Advanced |
| **Version** | Policy version, v1.0, v1.1 etc|
| **iOS/iPadOS** | Operating system |
| **MainCategory** | Name of main category, Device Configuration, Device Compliance etc|
| **SubCategory** | Name of sub category, MDE, AV, Disk etc|
| **Settings** | Short settings description |
| **Assignment** | Assignment scope- device (D) or user (U)|




## What's included in ALSO_IOS_MDE_AUTO_ONBOARDING?

This policy set is designed to automate the onboarding of Corporate Owned iOS and iPadOS devices to Microsoft Defender for Business and Microsoft Defender for Endpoint. 

This folder contains:


| Component | Description |
|-----------|-------------|
| Application | 1 Application: Microsoft Defender: Security for iOS and iPadOS | Auto installs on device once device are enrolled to Intune. Set as Required and Uninstall is not allowed. 
| Device Configuration Settings | 1 policy template: Auto onboarding to MDE policy template | Auto onboards device to Defender once device are enrolled to Intune
| App Configuration Policy | 1 policy templates: Sets Real Time protection and Network Protection ON automatically. This policy also enables organizations to use MDCA - Microsoft Defender for Cloud Apps on those devices.  

> [!IMPORTANT]
> All these policy templates and the application are required to enable seamless automatic onboarding of iOS and iPadOS devices to Microsoft Defender for Endpoint when they are enrolled in Intune.
> ALSO doesn't recommend to push out Defender application to BYOD devices for privacy reasons.


## What's included in ALSO_IOS_APP_PROTECTION_POLICIES?

This policy set is designed to secure Microsoft 365 content on BYOD and Corp devices together with Conditional Access policies.

| Component | Description |
|-----------|-------------|
| App Protection Policy | 1 policy templates: Restricts copy paste to Non- Microsoft apps, print and screen capture of Microsoft app content, backup to iCloud and other cloud services etc.


## What's included in ALSO_IOS_COMPLIANCE_POLICIES?

This policy set is designed to require compliant device at sign in together with Conditional Access policies.  

| Component | Description |
|-----------|-------------|
| CompliancePolicies | 4 policy templates: Requires minimum 6 digit PIN and ecryption, requires minimum OS version iOS/iPadOS 17.0, disallows jailbroken devices. Requires Defender compliance for corp devices etc. 


## What's included in ALSO_IOS_CA_POLICIES?

This policy set is designed to require compliant device at sign in together with Conditional Access policies.  

| Component | Description |
|-----------|-------------|
| ConnditionalAccess | 3 policy templates: 2 of them requires compliant device at sign in for admins and internals and 3rd one requires app protection policies for all users. 
| Groups | 3 Exclude groups for Conditional Access policies incl Break Glass Account group
| MigrationTable.json | Migration table needed to import groups

> [!IMPORTANT]
> **Always import Conditional Access policies in OFF mode**:



## Before importing (ALSO_IOS_MDE_AUTO_ONBOARDING) 

> [!IMPORTANT]
> **PLEASE ENSURE THAT YOU HAVE COMPLETED THESE STEPS, BEFORE YOU START IMPORTING**:

**Required administrator roles to do these steps**

Security Administrator and Intune Administrator roles + Conditional Access Administrator for Conditional Access policies 

> [!IMPORTANT]
> **Always import Conditional Access policies in OFF mode**:



**Device types supported** 
   - Works with both **personally-owned devices (work profile)** and **corporate-owned devices**

**Supported iOS versions**

Per September 2026:

iOS or iPadOS 17 or newer

Reference: Microsoft Learn


1. **Verify Defender for Business/Endpoint availability**
   - Go to [security.microsoft.com](https://security.microsoft.com)  
   - Navigate to **Assets → Devices** and ensure your Defender for Business / Defender for Endpoint instance is set up in the tenant.
  
<img width="1435" height="660" alt="image" src="https://github.com/user-attachments/assets/d4cd25aa-b369-4046-9fec-7af049784305" />


2. **Enable Intune connection in Defender portal**
   - Go to **System → Settings → Endpoints**  
   - Ensure that the **Microsoft Intune connection** is turned **ON**.
  
<img width="1846" height="996" alt="image" src="https://github.com/user-attachments/assets/020b15de-161a-4662-b787-e7a5ea2174f2" />


3. **Confirm Defender connection in Intune admin center**
   - Go to [intune.microsoft.com](https://intune.microsoft.com)  
   - Navigate to **Endpoint Security → Microsoft Defender for Endpoint**  
   - Ensure the **Connection status** is **Enabled**.
  
<img width="1030" height="353" alt="image" src="https://github.com/user-attachments/assets/4622ac18-83ec-47cf-9e15-92c883d00981" />

4. In same menu set these settings and Save

<img width="1203" height="1038" alt="image" src="https://github.com/user-attachments/assets/152232cb-6168-41d5-a024-50f9ffb59ef2" />


5. **Set up Apple MDM Push Certificate**
   - In the Intune admin center, go to **Devices → macOS → Enrollment**  
   - Ensure the **Apple MDM Push Certificate** is active.

  
<img width="1529" height="695" alt="image" src="https://github.com/user-attachments/assets/e48aa0c6-5b64-4157-a8df-a6ac80db084f" /> 
  

## How to import?

1. Download Micke M Intune Management Tool from here:  https://github.com/Micke-K/IntuneManagement
2. Extract folder and Start with start.cmd in the folder (works without local administrator rights on Windows and MacOS)
   
   <img width="635" height="247" alt="image" src="https://github.com/user-attachments/assets/ae7405c2-17cb-43a1-a96e-cd60181a2619" />

4. Command window and UI will open
5. Press on icon in upper right corner to sign in

   <img width="1311" height="965" alt="image" src="https://github.com/user-attachments/assets/2e835f79-5e07-4c7d-bd7c-5bd4976fde50" />

6. You may need a Global Administrator to consent to required API permissions first time if have not used these tool before. This can be done after sign-in by pressing same icon in upper right corner once more and press "Request Consent". Command Graph Command Line Tools application will be registered in Entra. Feel free to remove it after import or remove at least admin consent.

   <img width="294" height="145" alt="image" src="https://github.com/user-attachments/assets/675ebdc9-dc87-4633-bfa5-fbb92f7ba53d" />


7. After sign in and admin consent navigate to Bulk button in the left upper corner and press Import

   <img width="273" height="202" alt="image" src="https://github.com/user-attachments/assets/9e8b32ce-93fe-4ef8-9c19-325d138add8c" />

8. Download hole project and unzip

<img width="401" height="373" alt="image" src="https://github.com/user-attachments/assets/99f1e353-44f6-4bd5-85d7-0c2af71925f3" />

9. Choose Bulk-> Import and find right folder
   
   <img width="391" height="411" alt="image" src="https://github.com/user-attachments/assets/e03b2025-83fd-45c0-9122-25f29fbb3e69" />
   
10. Check "Add Object name to path" and Press Import

   <img width="2256" height="861" alt="image" src="https://github.com/user-attachments/assets/ec182c21-9982-4f57-ae03-07022f66fbff" />


## Issues?

Open issue here: 
