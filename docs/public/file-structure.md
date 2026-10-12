# File structure

[Documentation index](README.md)

## 📂 File Structure

The repository exposes exactly two cumulative, standalone packages:

```text
/
├── ALSO_IOS_BP/                  15 BP-compatible JSON artifacts
├── ALSO_IOS_E5/                  15 cumulative JSON artifacts
├── docs/public/
├── LICENSE
├── README.md
└── SECURITY
```

Both packages currently contain the same source membership because the repository has no E5-only source artifacts.

| Workload folder in each package | JSON files | Classification |
| --- | ---: | --- |
| `ALSO_IOS_MDE_AUTO_ONBOARDING` | 3 | BP |
| `ALSO_IOS_APP_PROTECTION_POLICIES` | 1 | BP |
| `ALSO_IOS_COMPLIANCE_POLICIES` | 4 | BP |
| `ALSO_IOS_CA_POLICIES` | 7 | BP |
| **Total** | **15** | **15 BP-compatible artifacts** |

## Historical source layout

The following original wording is retained to document how the source artifacts were organized before packaging:

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

See [Policy and configuration descriptions](policy-collections.md) for the original explanations and [How to import](how-to-import.md) for the illustrated workflow.
