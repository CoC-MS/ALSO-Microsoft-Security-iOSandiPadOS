https://github.com/user-attachments/assets/524c9224-fedf-45b6-a9d1-462480dd0b82
# The video shows the Windows repository, same logic applies to this


# 📥 How to import

[Documentation index](README.md)

## How to import?

> [!IMPORTANT]
> **Always import Conditional Access policies in OFF mode**:
> Ensure you have Conditional Access Administrator role before importing Conditional Access policies.

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

> [!WARNING]
> **We highly recommend extracting the downloaded folder to a OneDrive location. Otherwise, some policies with long filenames may fail to extract.**

<img width="401" height="373" alt="image" src="https://github.com/user-attachments/assets/99f1e353-44f6-4bd5-85d7-0c2af71925f3" />

9. Choose Bulk-> Import and find right folder
   
   <img width="391" height="411" alt="image" src="https://github.com/user-attachments/assets/e03b2025-83fd-45c0-9122-25f29fbb3e69" />
   
10. Check "Add Object name to path" and Press Import

   <img width="2256" height="861" alt="image" src="https://github.com/user-attachments/assets/ec182c21-9982-4f57-ae03-07022f66fbff" />

## After importing

Review imported settings, tenant-specific references, exclusions, and assignments before assigning policies. Keep Conditional Access policies OFF until they have been validated with pilot users and emergency-access exclusions.
