# ☁️ Defender for Cloud Apps/Defender for Business Custom Indicators and Web Content Filtering

[Documentation index](README.md)

## What's included in ALSO_IOS_MDE_AUTO_ONBOARDING?


| App Configuration Policy | 1 policy templates: Sets Real Time protection and Network Protection ON automatically. This policy also enables organizations to use MDCA - Microsoft Defender for Cloud Apps on those devices.  

# ☁️ Defender for Cloud Apps

[Documentation index](README.md)

## What's included in ALSO_MACOS_MDCA_READY/SettingsCatalog

This policy is designed to help organizations get started with Microsoft Defender for Cloud Apps cloud app blocking and monitoring. It includes the required Real-Time Protection, Network Protection, and Cloud Protection settings, reducing the need for manual configuration.

This folder contains:

| Component | Description |
|-----------|-------------|
| Settings Catalog Policies | 1 policy template:  AV Configuration |

> [!IMPORTANT]
> ALSO_IOS/IPADOS_MDE_AUTO_ONBOARDING must be imported and assigned to the target device group before deploying any other policies in this package.
> This policy will also work with Microsoft 365 Business Premium, but it uses Custom Indicators in Microsoft Defender rather than the cloud app catalog available through Microsoft Defender for Cloud Apps.

The single `ALSO_MACOS_MDCA_READY` AV Configuration export is the starter policy included in both packages. Its Business Premium compatibility is limited to the Custom Indicators workflow described below. All other Defender for Cloud Apps policies cannot be used with Business Premium and therefore belong only in `ALSO_MACOS_E5`. No additional Defender for Cloud Apps policies are present in the current source artifacts.

## Before importing ALSO_MACOS_MDCA_READY 

> [!IMPORTANT]
> **PLEASE ENSURE THAT YOU HAVE COMPLETED THESE STEPS, BEFORE YOU START USING THIS POLICY**
> **ALSO DON'T RECCOMEND TO USE CUSTOM NETWORK INDICATORS, WEB CONTENT FILTERING AND DEFENDER FOR CLOUD APPS ON WORK PROFILE DEVICE FOR PIRVACY REASONS. ONLY FULLY MANAGED CORPORATE IOS AND IPADOS DEVICE**

**Required administrator roles to do these steps**

Security Administrator

**Device types supported**
   - Works with both **personally-owned devices (work profile)** and **corporate-owned devices**


## For Defender for Cloud Apps licensed tenants with Defender for Endpoint P2 (E5 package)

1. Navigate to security.microsoft.com -> Settings -> Cloud Apps

Direct link: https://security.microsoft.com/cloudapps/settings?tabid=about&tid 

<img width="1513" height="1165" alt="image" src="https://github.com/user-attachments/assets/fc9c923d-144c-42c1-a900-5b193c56908e" />

2. Ensure you check "Enforce App Access" and Save.

<img width="1429" height="949" alt="image" src="https://github.com/user-attachments/assets/4f324487-6b4a-476a-9f3b-5629d57a1331" />

3. Navigate to Endpoint section in settings and toggle this one ON (Microsoft Defender For Cloud Apps and Save

<img width="1607" height="1224" alt="image" src="https://github.com/user-attachments/assets/f34133fb-1356-4b2a-9133-ac2f693271f6" />

4. You can now block and monitor apps for Cloud Apps -> Cloud Apps catalog section after your policy have been pushed out to your Mac devices.

PS: Keep in mind that it can take up to 24 hours before it's fully active. 

## For Defender for Business licensed tenants (BP package)


1. Navigate to security.microsoft.com -> Settings -> Endpoints

Direct link: https://security.microsoft.com/securitysettings/endpoints/integration?

2. Check that Custom Network Indicators and Web Content filtering are toggled ON

<img width="1922" height="1247" alt="image" src="https://github.com/user-attachments/assets/b544ad55-118f-44ec-b672-82ec154c4847" />







