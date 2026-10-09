# 📂 File structure

[Public documentation](README.md) | [Repository preview](../../README.preview.md)

The repository contains four purpose-specific sets. There are no generated licensing packages or build manifests. Folder names below are the actual checked-in names.

```text
ALSO-Microsoft-Security-iOSandiPadOS/
├── ALSO_IOS_APP_PROTECTION_POLICIES/
│   └── AppProtection/                 1 JSON policy
├── ALSO_IOS_CA_POLICIES/
│   ├── ConditionalAccess/             3 JSON policies
│   ├── Groups/                        3 JSON group exports
│   └── MigrationTable.json            Import reference metadata
├── ALSO_IOS_COMPLIANCE_POLICIES/
│   └── CompliancePolicies/            4 JSON policies
├── ALSO_IOS_MDE_AUTO_ONBOARDING/
│   ├── Applications/                  1 JSON iOS Store app export
│   ├── AppConfigurationManagedDevice/ 1 JSON app configuration
│   └── DeviceConfiguration/           1 JSON VPN profile
├── docs/public/                       Preview deployment guidance
├── README.preview.md                  Proposed root README
├── README.md                          Existing README, unchanged
├── LICENSE
├── SECURITY
└── .github/                           Existing issue templates
```

## 📦 Workload inventory

| Folder | JSON files | Resource type / role |
| --- | ---: | --- |
| [AppProtection](../../ALSO_IOS_APP_PROTECTION_POLICIES/AppProtection) | 1 | `iosManagedAppProtection`; targets all Microsoft apps (`allMicrosoftApps`). |
| [ConditionalAccess](../../ALSO_IOS_CA_POLICIES/ConditionalAccess) | 3 | CA005 app protection, CA110 administrator compliance, CA210 all-user compliance; all exported `disabled`. |
| [Groups](../../ALSO_IOS_CA_POLICIES/Groups) | 3 | Emergency-access exclusion group and CA005/CA110 exclusion groups. |
| [MigrationTable.json](../../ALSO_IOS_CA_POLICIES/MigrationTable.json) | 1 | Source group names/IDs and tenant metadata for import reference mapping; not a deployable policy. |
| [CompliancePolicies](../../ALSO_IOS_COMPLIANCE_POLICIES/CompliancePolicies) | 4 | `iosCompliancePolicy`; three BYOD-labelled checks and one corporate Defender-risk check. |
| [Applications](../../ALSO_IOS_MDE_AUTO_ONBOARDING/Applications) | 1 | `iosStoreApp` for Microsoft Defender: Security (`com.microsoft.scmx`), not an app binary or volume-purchase token. |
| [AppConfigurationManagedDevice](../../ALSO_IOS_MDE_AUTO_ONBOARDING/AppConfigurationManagedDevice) | 1 | `iosMobileAppConfiguration`; enables Web Protection and Network Protection and references the source app ID. |
| [DeviceConfiguration](../../ALSO_IOS_MDE_AUTO_ONBOARDING/DeviceConfiguration) | 1 | `iosVpnConfiguration`; Defender loopback VPN with `SilentOnboard`, `AutoOnboard`, and `SingleSignOn` set to `True`. |

**Total: 15 JSON files**, comprising 10 policy exports, 1 app export, 3 group exports, and 1 migration table. These are repository-file counts, not evidence of assignments or successful deployment.

## ✅ Compliance checks

| Export name fragment | Verified settings | Review point |
| --- | --- | --- |
| `BYOD - Device properties min. OS version 17` | `osMinimumVersion=17.0` | A compliance threshold, not a guarantee of current app/service support. |
| `BYOD - Jailbroken status and Threat Status` | Jailbreak blocking enabled; `deviceThreatProtectionEnabled=false` | The name does not establish active MTD risk enforcement. |
| `BYOD - PIN and screen lock` | Passcode required; numeric; minimum length 6; simple PIN blocked; lock/inactivity values 5 minutes | Device PIN, distinct from the app protection PIN. |
| `Corp - MDE- Risk score requirements` | `deviceThreatProtectionEnabled=true`; `advancedThreatProtectionRequiredSecurityLevel=medium` | Requires Defender integration, onboarding, and working risk reporting. |

All four export a noncompliance `block` action with **zero grace hours**. Review timing before assignment. The corporate MDE policy does not itself include the separate OS/PIN/jailbreak baseline checks; evaluate those separately for the intended managed-device population.

## 🔗 Dependencies and boundaries

Keep the CA `Groups` folder and `MigrationTable.json` with the CA exports when using the import tool's reference mapping. Do not reuse source tenant/group IDs as target assignments. Group exports do not provision your emergency-access accounts or prove their membership.

Import or select the target Defender app before resolving the managed-device app configuration's `targetedMobileApps` reference. Review the VPN profile against the target enrollment/supervision scenario. The repository does not include Apple enrollment profiles, push certificates, Apple Business Manager tokens, Authenticator/SSO profiles, supervised Control Filter profiles, or Defender for Cloud Apps policies.

See [How to import](how-to-import.md) for the sequence and [Naming exceptions](short-name-exceptions.md) for existing name differences.
