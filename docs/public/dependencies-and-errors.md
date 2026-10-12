# 🧩 Dependencies and special handling

[Documentation index](README.md) | [Repository README](../../README.md)

The source README does not document specific import error messages. It does document these dependencies and handling requirements verbatim:

> [!IMPORTANT]
> All these policy templates and the application are required to enable seamless automatic onboarding of iOS and iPadOS devices to Microsoft Defender for Endpoint when they are enrolled in Intune.
> ALSO doesn't recommend to push out Defender application to BYOD devices for privacy reasons.

> [!IMPORTANT]
> **Always import Conditional Access policies in OFF mode**:

The required roles are preserved in [General prerequisites](general-prerequisites.md), the Defender/Intune and Apple preparation is preserved in [iOS/iPadOS prerequisites](ios-ipados-prerequisites.md), and the illustrated import flow is preserved in [How to import](how-to-import.md).
