# 🏷️ Naming exceptions

[Public documentation](README.md) | [Repository preview](../../README.preview.md) | [Policy naming](policy-naming.md)

Several real exports depart from the full descriptive naming convention. Keep their original names when locating files and validating migration mappings; this preview does not rename policies.

| Existing name / fragment | Meaning and caution |
| --- | --- |
| `ALSO - Compliance - ...` | Compliance names omit impact, license, baseline, and version markers. Missing markers do not mean no licensing or enrollment prerequisites. |
| `Microsoft Defender Security.json` | Short filename for the `Microsoft Defender: Security` Store app. No baseline/license/scope markers or required assignment are implied. |
| `ALSO-CA-BSAccounts- Exclude` | Emergency-access exclusion group referenced by all three CA exports; no accounts or verified membership are supplied. |
| `RequireAppProtectionPoliciy` | Existing spelling in CA005's filename and display name, not a different control. Its grant is `compliantApplication` (require app protection). |
| CA005 exclusion group ending `RequireAppEnforcedRestrictions- Exclude` | The group name refers to a different control than CA005's current app-protection grant and uses `Office365` rather than `Microsoft365`. Resolve it through the migration/reference mapping, not name guesses. |
| CA210 `Internals` | Despite the audience label, the actual export includes `All` users with no guest/external-user exclusion. Review target scope explicitly. |
| `iOSAndAndroid` / `iOSandAndroid` | All CA exports include both Android and iOS. Other policies here are iOS-specific; Android protection/compliance dependencies are not supplied. |
| `BYOD - Jailbroken status and Threat Status` | Jailbreak blocking is enabled, but `deviceThreatProtectionEnabled=false`; the name is not proof of active threat-risk enforcement. |

Full-style names omit the documented `v1.0` component and vary in spacing. Display names use `iOS/iPadOS`; filenames use `iOSiPadOS`. `Corp` and `BYOD` are descriptive labels, not automatic ownership filters. The CA005 device filter is an actual exported exception for devices that are **both compliant and company-owned**.

Use the actual JSON settings and target-tenant objects as the source of truth. Do not infer assignments, licensing, current OS support, or deployment success from a short name or a `D` suffix.
