# 🧩 Dependencies and special handling

[Documentation index](README.md)

## Microsoft Defender for Endpoint onboarding dependency

> [!IMPORTANT]
> All these policy templates and the application are required to enable seamless automatic onboarding of iOS and iPadOS devices to Microsoft Defender for Endpoint when they are enrolled in Intune.
> ALSO doesn't recommend to push out Defender application to BYOD devices for privacy reasons.

The chosen package keeps the application, app configuration, and device configuration exports together under `ALSO_IOS_MDE_AUTO_ONBOARDING`.

## Defender for Cloud Apps statement

| App Configuration Policy | 1 policy templates: Sets Real Time protection and Network Protection ON automatically. This policy also enables organizations to use MDCA - Microsoft Defender for Cloud Apps on those devices.  

See [Defender for Cloud Apps](defender-cloud-apps.md) for the complete preserved licensing statements. No separate Defender for Cloud Apps export or E5-only artifact exists in the current source set.

## Conditional Access

> [!IMPORTANT]
> **Always import Conditional Access policies in OFF mode**:

Ensure you have Conditional Access Administrator role before importing Conditional Access policies.

The `ALSO_IOS_CA_POLICIES` workload contains three Conditional Access policy templates, three group templates, and `MigrationTable.json`. Keep these files together in the chosen package and review group references, exclusions, assignments, and migration mappings before enabling any policy.

## Documented errors

The source README does not document specific import error messages. Follow [How to import](how-to-import.md), retain the workload folders, and review tool output before retrying an import.
