# 📦 Licensing and package guidance

[Documentation index](README.md) | [Repository README](../../README.md)

The repository exposes exactly two standalone packages. `ALSO_IOS_BP` contains all 15 Business Premium-compatible source artifacts. `ALSO_IOS_E5` is cumulative and contains the same 15 artifacts because no current source artifact is classified as E5-only.

The original README wording follows verbatim. Its historical count of 39 is retained for lossless preservation; the verified current package count is 15.

## iOS/iPadOS Licensing Guide

Choose one standalone package. The packages are cumulative: E5 contains every BP-compatible export plus any E5-only exports. The current repository has no E5-only exports, so both packages contain the same 39 source artifacts.

### ✅ E5 Folder (Full Experience)

Package: 

The **E5 folder** is intended for organizations that have access to the complete Microsoft Security stack used by these templates.

| License | Supported |
|----------|----------|
| Microsoft 365 E7 | ✅ Full support |
| Microsoft 365 E5 | ✅ Full support |
| Microsoft 365 E3 + Defender Suite | ✅ Full support |
| Business Premium + Defender Suite | ✅ Full support |
| Microsoft 365 F3 + Defender Suite | ✅ Full support |
| Microsoft 365 F1 + Defender Suite | ✅ Full support |

### ✅ BP Folder (Limited Experience)

Package: 

The **Business Premium folder** is designed for organizations using Microsoft 365 Business Premium and other licenses with partial feature compatibility.

| License | Supported Features |
|----------|----------|
| Microsoft 365 Business Premium | ⚠️ Supported with limitations (without full Defender for Cloud Apps experience) |
| Microsoft 365 E3 | ⚠️ Supported with limitations (without full Defender for Cloud Apps experience) |
| Microsoft 365 F3 | ⚠️ Supported with limitations (without full Defender for Cloud Apps experience) |
| Microsoft 365 F1 | ⚠️ Intune settings only. Defender settings are not supported. |

#### Microsoft 365 F3 Limitations

For Microsoft 365 F3, only the following Microsoft Defender security settings are supported:

- Defender Antivirus


> **Important:** Microsoft 365 F1 supports deployment of Intune configuration settings only. Microsoft Defender security policy settings included in this repository are not supported with F1 licensing.


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
