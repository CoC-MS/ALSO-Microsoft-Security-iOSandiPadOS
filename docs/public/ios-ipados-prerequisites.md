# 📱 iOS and iPadOS prerequisites

[Public documentation](README.md) | [Repository preview](../../README.preview.md)

Complete the [General prerequisites](general-prerequisites.md), then prepare only the services needed for your selected scenario. Portal labels can move; use the named setting and Microsoft's current guidance.

## 👤 BYOD versus corporate-managed

| Scenario | Preparation and limits |
| --- | --- |
| **MAM-only BYOD** | Use supported Intune-protected apps and work accounts; configure app protection and its intended CA controls. iOS app-based CA requires Microsoft Authenticator as the broker. Device compliance and managed-device configuration require enrollment and are not a MAM-only substitute. |
| **Enrolled personal device** | Choose a supported Apple enrollment method and verify available settings. Apple User Enrollment differs from full device enrollment; it is not an Android-style work profile. Review privacy, user communication, and enrollment restrictions. |
| **Corporate-managed device** | Confirm ownership, user affinity, enrollment method, and supervision independently. Deploy Defender and configuration only to the reviewed managed-device population. Corporate ownership does not by itself enable zero-touch onboarding. |

The repository's guidance discourages pushing Defender to BYOD for privacy reasons. These exports do not include a BYOD-specific Defender MAM configuration. A separate supported design and privacy review would be needed for that use.

> [!IMPORTANT]
> MAM app protection can protect work data without MDM enrollment, but that does not make a device compliant. CA110 and CA210 require a compliant device. Adjust the target design and CA scope deliberately if unenrolled BYOD must remain usable.

## 🍎 Apple enrollment and platform

| Requirement | When it applies |
| --- | --- |
| Active Apple MDM Push certificate | Intune iOS/iPadOS enrollment. Check **Devices > Enrollment > Apple > Apple MDM Push certificate** and maintain renewal using the correct Apple account. Not required just to apply MAM-only app protection. |
| Apple Business Manager / Apple School Manager enrollment token | When using Automated Device Enrollment. Configure the connection and enrollment profiles outside this repository. |
| Apps and Books token / app licensing | When deploying volume-purchased apps. The checked-in Defender export is an **iOS Store app**, not a volume-purchased app. |
| Enrollment apps and identity setup | Company Portal, Microsoft Authenticator, SSO extension, and registration requirements vary by enrollment method. Follow the selected enrollment method's Microsoft guidance; these dependencies are not included here. |
| Supported OS/app versions | The OS compliance export requires `17.0`. The app export's minimum-OS metadata is `16.0`, whereas Microsoft's current Defender deployment guidance specifies `17.0`. Confirm current support and update target app settings before assignment. A stored export value is not a current support statement. |

## 🛡️ Defender and Intune connection

For corporate Defender deployment and the MDE-risk compliance policy:

1. Confirm that the [Defender portal](https://security.microsoft.com/) is provisioned and the relevant users are licensed.
2. In Defender **Settings > Endpoints > Advanced features**, enable **Microsoft Intune connection** and save.
3. In [Intune](https://intune.microsoft.com/), open **Endpoint security > Microsoft Defender for Endpoint**, confirm the connection, and enable **Connect iOS/iPadOS devices to Microsoft Defender for Endpoint** under compliance evaluation for the device-risk scenario.
4. Review app protection evaluation options only if designing Defender-risk conditional launch for MAM. The checked-in app protection export has `maximumAllowedDeviceThreatLevel=notConfigured`; it does not establish a Defender-risk MAM requirement.
5. Deploy the Defender app and validate configuration delivery, onboarding, device inventory, and risk reporting before enforcing MDE-risk compliance or CA.

## ⚙️ Onboarding configuration limits

| Export | What to verify |
| --- | --- |
| Defender Store app | Import/create the app, then configure a reviewed **Required** assignment for the corporate pilot. The export is unassigned; required installation and uninstall restrictions are not guaranteed by this file. |
| Managed-device app configuration | Map the source `targetedMobileApps` ID to the actual target Defender app. The two exported string settings are `WebProtection=true` and `DefenderNetworkProtectionEnable=true`. These are iOS protection controls, not Windows real-time antivirus settings. |
| Defender VPN profile | Uses `127.0.0.1` and `com.microsoft.scmx`, with `SilentOnboard`, `AutoOnboard`, and `SingleSignOn` set to `True`. This is a local-loopback protection VPN, not a corporate remote-access VPN. Review compatibility with other VPNs and select the supported onboarding design rather than treating the combined keys as universally valid. |

Microsoft documents **zero-touch** and **automatic VPN onboarding** as separate options; do not combine their procedures blindly. Zero-touch requires a supported user-affinity scenario, and sign-in may still be needed after authentication changes. Network Protection initialization can require the user to open Defender once.

For **supervised devices**, Microsoft's guidance uses the `issupervised` app configuration and a Control Filter profile, including a zero-touch variant. Neither is included in this repository. For **Apple User Enrollment**, device-wide VPN deployment and these VPN onboarding methods are not supported; separate SSO, app configuration, and volume-purchased app preparation is required.

Defender on iOS does not provide the Windows antivirus/EDR feature set. Do not interpret the app configuration as malware scanning, Windows EDR-in-block-mode configuration, mobile web content filtering, or automatic Defender for Cloud Apps discovery. Confirm optional integrations independently.

## 📚 Microsoft sources

- [Enroll iOS and iPadOS devices in Intune](https://learn.microsoft.com/en-us/intune/intune-service/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Apple MDM Push certificate](https://learn.microsoft.com/en-us/intune/intune-service/enrollment/apple-mdm-push-certificate-get)
- [App protection overview](https://learn.microsoft.com/en-us/intune/app-management/protection/overview)
- [Require app protection with Conditional Access](https://learn.microsoft.com/en-us/entra/identity/conditional-access/policy-all-users-approved-app-or-app-protection)
- [Deploy Defender on iOS: supervision, zero-touch, VPN, and User Enrollment](https://learn.microsoft.com/en-us/defender-endpoint/ios-install)
- [Configure Defender iOS features and limitations](https://learn.microsoft.com/en-us/defender-endpoint/ios-configure-features)
- [Configure Defender and Intune integration](https://learn.microsoft.com/en-us/intune/device-security/microsoft-defender/configure-integration)
