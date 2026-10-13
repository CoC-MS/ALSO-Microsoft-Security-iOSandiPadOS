# 🚀 General prerequisites

[Documentation index](README.md)

> [!IMPORTANT]
> **⚠️ IMPORTANT: Read this before importing and using any policies.**

Choose either [`ALSO_IOS_BP`](../../ALSO_IOS_BP) or [`ALSO_IOS_E5`](../../ALSO_IOS_E5) using the [iOS/iPadOS Licensing Guide](../../README.md#iosipados-licensing-guide). Review each policy, licence requirement, setting, tenant-specific value, dependency, and assignment before import.

**Required administrator roles to do these steps**

Security Administrator and Intune Administrator roles + Conditional Access Administrator for Conditional Access policies 

For Conditional Access:

> [!IMPORTANT]
> **Always import Conditional Access policies in OFF mode**:
> Ensure you have Conditional Access Administrator role before importing Conditional Access policies and that your Security defaults are turned off. To check if your tenant are using Security defaults use this direct link here:

https://entra.microsoft.com/#view/Microsoft_AAD_IAM/TenantOverview.ReactView/initialValue//tabId//recommendationResourceId//fromNav/Identity

<img width="1559" height="197" alt="image" src="https://github.com/user-attachments/assets/b947568d-76d3-4a93-ae4a-5e293c68e59a" />

Use [iOS/iPadOS prerequisites](ios-ipados-prerequisites.md) for the original service and enrollment preparation, [Defender for Cloud Apps](defender-cloud-apps.md) for the exact authored MDCA and licensing statements, and [Dependencies and special handling](dependencies-and-errors.md) for onboarding, privacy, and Conditional Access dependencies.


## Before importing (ALSO_IOS_MDE_AUTO_ONBOARDING) 

> [!IMPORTANT]
> **PLEASE ENSURE THAT YOU HAVE COMPLETED THESE STEPS, BEFORE YOU START IMPORTING**:
> **ALSO DON'T RECCOMEND TO ONBOARD DEVICES WITH WORK PROFILE TO DEFENDER FOR PRIVACY REASONS, ONLY FULLY MANAGED IOS/IPAD DEVICES**  

**Required administrator roles to do these steps**

Security Administrator and Intune Administrator roles + Conditional Access Administrator for Conditional Access policies 


1. **Verify Defender for Business/Endpoint availability**
   - Go to [security.microsoft.com](https://security.microsoft.com)  
   - Navigate to **Assets → Devices** and ensure your Defender for Business / Defender for Endpoint instance is set up in the tenant.
  
  Direct link: https://security.microsoft.com/machines?category=all-devices

  
<img width="1435" height="660" alt="image" src="https://github.com/user-attachments/assets/d4cd25aa-b369-4046-9fec-7af049784305" />

2. **Enable Intune connection in Defender portal**
   - Go to **System → Settings → Endpoints**  
   - Ensure that the **Microsoft Intune connection** is turned **ON**.
  
Direct link: https://security.microsoft.com/securitysettings/endpoints/integration?
  
<img width="1846" height="996" alt="image" src="https://github.com/user-attachments/assets/020b15de-161a-4662-b787-e7a5ea2174f2" />

3. **Confirm Defender connection in Intune admin center**
   - Go to [intune.microsoft.com](https://intune.microsoft.com)  
   - Navigate to **Endpoint Security → Microsoft Defender for Endpoint**  
   - Ensure the **Connection status** is **Enabled**.
  
Direct link: https://intune.microsoft.com/#view/Microsoft_Intune_Workflows/SecurityManagementMenu/~/atp
  
<img width="1030" height="353" alt="image" src="https://github.com/user-attachments/assets/4622ac18-83ec-47cf-9e15-92c883d00981" />

4. In same menu set these settings and Save

<img width="1203" height="1038" alt="image" src="https://github.com/user-attachments/assets/152232cb-6168-41d5-a024-50f9ffb59ef2" />

5. **Set up Apple MDM Push Certificate**
   - In the Intune admin center, go to **Devices → macOS → Enrollment**  
   - Ensure the **Apple MDM Push Certificate** is active.

Direct link: https://intune.microsoft.com/#view/Microsoft_Intune_DeviceSettings/DevicesMacOsMenu/~/appleEnrollment 

  
<img width="1529" height="695" alt="image" src="https://github.com/user-attachments/assets/e48aa0c6-5b64-4157-a8df-a6ac80db084f" /> 
