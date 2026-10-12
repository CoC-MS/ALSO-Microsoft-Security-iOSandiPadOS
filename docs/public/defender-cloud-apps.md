# ☁️ Defender for Cloud Apps

[Documentation index](README.md)

## What's included in ALSO_IOS_MDE_AUTO_ONBOARDING?

The source workload description contains this exact statement:

| App Configuration Policy | 1 policy templates: Sets Real Time protection and Network Protection ON automatically. This policy also enables organizations to use MDCA - Microsoft Defender for Cloud Apps on those devices.  

The source README contains the following exact licensing limitations:

| License | Supported Features |
|----------|----------|
| Microsoft 365 Business Premium | ⚠️ Supported with limitations (without full Defender for Cloud Apps experience) |
| Microsoft 365 E3 | ⚠️ Supported with limitations (without full Defender for Cloud Apps experience) |
| Microsoft 365 F3 | ⚠️ Supported with limitations (without full Defender for Cloud Apps experience) |
| Microsoft 365 F1 | ⚠️ Intune settings only. Defender settings are not supported. |

No separate Defender for Cloud Apps export or E5-only artifact exists in the current source set. Both cumulative packages therefore contain the same 15 files. Review feature entitlement and the actual iOS/iPadOS export settings before deployment; no macOS-specific Custom Indicators or Cloud App Catalog workflow is asserted here.
