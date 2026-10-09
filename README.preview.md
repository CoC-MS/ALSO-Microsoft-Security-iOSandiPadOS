# 🛡️ ALSO Microsoft Security - iOS and iPadOS

> Microsoft Intune and Microsoft Entra policy exports for protecting Microsoft 365 app data, assessing device compliance, controlling access, and onboarding corporate-managed iOS/iPadOS devices to Microsoft Defender.

> [!NOTE]
> **Documentation preview:** The main `README.md` is unchanged. Replacement is manual: copy or rename this file to `README.md` when approved, then update the preview backlinks in `docs/public` and remove this notice. The resource links below work from either root filename.

> [!IMPORTANT]
> These exports are starting points, not ready-made tenant configurations. Confirm licensing, enrollment support, settings, tenant-specific references, dependencies, and assignments. Pilot before expanding deployment; maintain a rollback plan. Read the repository's [security and usage notice](SECURITY).

| Resource | Description |
| --- | --- |
| 📚 **[Public documentation](docs/public/README.md)** | Browse deployment guidance. |
| 🚀 **[General prerequisites](docs/public/general-prerequisites.md)** | Check licensing, permissions, and deployment readiness. |
| 📱 **[iOS/iPadOS prerequisites](docs/public/ios-ipados-prerequisites.md)** | Review enrollment, Apple services, Defender integration, and privacy. |
| 📖 **[Policy naming](docs/public/policy-naming.md)** | Understand the documented convention and actual exported names. |
| 🏷️ **[Naming exceptions](docs/public/short-name-exceptions.md)** | Review short names, spelling differences, and scope mismatches. |
| 📂 **[File structure](docs/public/file-structure.md)** | Find the four workload sets and supporting metadata. |
| 📥 **[How to import](docs/public/how-to-import.md)** | Import selected resources safely and validate deployment. |
| 🐛 **[Reporting issues](docs/public/reporting-issues.md)** | Report problems without exposing tenant information. |
| 📜 **[License](LICENSE)** | Read the Apache License 2.0. |

---

## 📦 Policy sets

These are JSON exports, not an iOS application, package generator, or complete enrollment solution. The sets are organized by purpose; there are no BP/E3/E5 build packages, Basic/Adv editions, or build manifests here.

| Set | Checked-in resources | Purpose |
| --- | --- | --- |
| [App protection](ALSO_IOS_APP_PROTECTION_POLICIES/AppProtection) | 1 app protection policy | Protect Microsoft app work data on BYOD and corporate devices. |
| [Conditional Access](ALSO_IOS_CA_POLICIES) | 3 CA policies, 3 exclusion groups, 1 migration table | Require app protection or device compliance for the selected sign-in scenarios. |
| [Compliance](ALSO_IOS_COMPLIANCE_POLICIES/CompliancePolicies) | 4 compliance policies | Separate OS-version, jailbreak, PIN/lock, and corporate Defender-risk checks. |
| [Defender onboarding](ALSO_IOS_MDE_AUTO_ONBOARDING) | 1 app export, 1 managed-device app configuration, 1 VPN profile | Support Defender deployment and onboarding on corporate-managed devices. |

Counts describe checked-in JSON files, not tenant assignments or installed applications. `MigrationTable.json` is import metadata, not a policy. See [File structure](docs/public/file-structure.md) for the exact workload layout.

## 🌐 Coverage and deployment scenarios

| Area | Included content and limits |
| --- | --- |
| 🔒 **App protection (MAM)** | Microsoft-app targeting, a six-digit app PIN, managed-app outbound data/clipboard controls, backup and printing blocks, and screen capture, Genmoji, and Writing Tools blocks. Enforcement depends on supported app/SDK and OS versions. |
| ✅ **Device compliance (MDM)** | Minimum OS `17.0`; jailbreak blocking; six-digit numeric device passcode with simple PINs blocked and five-minute lock settings; a separate corporate MDE risk policy with a `medium` threshold. These checks are split across four exports, not one universal baseline. |
| 🔐 **Conditional Access** | CA005 targets Office 365 and requires app protection; CA110 targets selected administrator roles and requires compliance; CA210 targets all users and requires compliance. **All three include Android as well as iOS and are exported disabled.** |
| 🛡️ **Defender onboarding** | An iOS Store app export for Microsoft Defender, `WebProtection=true` and `DefenderNetworkProtectionEnable=true` app settings, and a local-loopback VPN profile with onboarding keys. Assignment and enrollment-specific preparation remain necessary. |

| Scenario | Recommended review path |
| --- | --- |
| **BYOD without device enrollment (MAM-only)** | Start with app protection and review CA005 for the intended apps/users. Device compliance policies and the managed-device Defender onboarding set do not apply to unenrolled devices. CA110/CA210 can still block those users by requiring a compliant device. |
| **Enrolled BYOD** | Evaluate Apple enrollment capabilities, privacy, and the BYOD-labelled compliance checks. This repository does not recommend pushing its corporate Defender onboarding set to personal devices. |
| **Corporate-managed** | Review app protection, required baseline compliance checks, Defender onboarding dependencies, and the corporate MDE risk check. Corporate ownership alone does not imply supervision or support for silent onboarding. |

> [!WARNING]
> Keep Conditional Access **Off** during import and reference validation. CA210's `Internals` name does not limit its exported scope: it includes **All users**. Resolve emergency-access exclusions and validate the combined effect of all CA policies before report-only testing and staged enforcement. CA005 excludes devices only when they are both compliant and company-owned; it is not simply a BYOD-only policy.

The app export has no required-install assignment. The VPN and app configuration do not guarantee installation, non-removability, or interaction-free onboarding. This set contains no supervised Control Filter profile or Apple enrollment configuration. It also does not establish Defender for Cloud Apps integration or entitlement.

---

## 🚀 Getting started

1. ✅ Review [General prerequisites](docs/public/general-prerequisites.md) and [iOS/iPadOS prerequisites](docs/public/ios-ipados-prerequisites.md).
2. 📂 Select resources by scenario using [File structure](docs/public/file-structure.md); do not import everything by default.
3. 📥 Follow [How to import](docs/public/how-to-import.md), validate references and pilot outcomes, then expand in stages.
