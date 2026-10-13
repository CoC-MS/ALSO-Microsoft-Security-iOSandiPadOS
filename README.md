# 🛡️ ALSO Microsoft Security iOS and iPadOS Policy Templates

> Collection of Microsoft Security policy templates for iOS and iPadOS devices, covering both BYOD (Bring Your Own Device) and corporate-managed deployments. Includes automated onboarding to Microsoft Defender, App Protection Policies (MAM), App Configuration Policies, Compliance Policies, and Device Configuration Profiles to help organizations secure mobile devices while maintaining a productive user experience..

**Works with Business Premium and up.**

---

> [!IMPORTANT]
> **⚠️ IMPORTANT: Read this before importing and using any policies.**

## iOS/iPadOS Licensing Guide

Choose one standalone package. 

### ✅ E5 Folder (Full Experience)
 

Package: [`ALSO_IOS_E5`](ALSO_IOS_E5)

The **E5 folder** is intended for organizations that have access to full experience of Defender for Cloud apps with these licenses. 

| License | Supported |
|----------|----------|
| Microsoft 365 E7 | ✅ Full support |
| Microsoft 365 E5 | ✅ Full support |
| Microsoft 365 E3 + Defender Suite | ✅ Full support |
| Business Premium + Defender Suite | ✅ Full support |
| Microsoft 365 F3 + Defender Suite | ✅ Full support |
| Microsoft 365 F1 + Defender Suite | ✅ Full support |

### ⚠️ BP Folder (Limited Experience)

Package: [`ALSO_IOS_BP`](ALSO_IOS_BP)

The **Business Premium folder** is designed for organizations using Microsoft 365 Business Premium and other licenses with partial feature compatibility.

| License | Supported Features |
|----------|----------|
| Microsoft 365 Business Premium | ⚠️ Supported with limitations (without full Defender for Cloud Apps experience) |
| Microsoft 365 E3 | ⚠️ Supported with limitations (without full Defender for Cloud Apps experience) |
| Microsoft 365 F3 | ⚠️ Supported with limitations (without full Defender for Cloud Apps experience) |
| Microsoft 365 F1 | ⚠️ Intune settings only. Defender settings are not supported. |


> **Important:** Microsoft 365 F1 supports deployment of Intune configuration settings only. Microsoft Defender security policy settings included in this repository are not supported with F1 licensing.

---

| Resource | Description |
| --- | --- |
| 📚 **[Documentation index](docs/public/README.md)** | Browse all deployment documentation. |
| 📖 **[Policy and configuration descriptions](docs/public/policy-collections.md)** | Review the preserved descriptions of every workload collection. |
| 🚀 **[General prerequisites](docs/public/general-prerequisites.md)** | Review roles, licensing, and deployment preparation. |
| 📱 **[iOS/iPadOS prerequisites](docs/public/ios-ipados-prerequisites.md)** | Prepare Defender, Intune, and Apple enrollment. |
| ☁️ **[Defender for Cloud Apps/Defender for Business Custom Indicators and Web Content Filtering](docs/public/defender-cloud-apps.md)** | Review which settings needs to be turned on and all limitations. |
| 📖 **[Policy naming](docs/public/policy-naming.md)** | Understand licence tags and naming components. |
| 📂 **[File structure](docs/public/file-structure.md)** | Compare the two cumulative packages and workload folders. |
| 📥 **[How to import](docs/public/how-to-import.md)** | Follow the original illustrated import guidance. |
| 🐛 **[Reporting issues](docs/public/reporting-issues.md)** | Open an issue. |
| 🛡️ **[Security information](SECURITY)** | Read the security and usage information. |
| 📜 **[License](LICENSE)** | Read the repository licence. |

---

## 📦 iOS/iPadOS packages

Each package is standalone and retains the original workload folders and exact export bytes.

Choose one standalone package. The packages are cumulative: E5 contains every BP-compatible export plus any E5-only exports. All 15 current source artifacts are Business Premium-compatible, so both packages contain the same files and there are no E5-only artifacts.

| Package | Classification | JSON files |
| --- | --- | ---: |
| [`ALSO_IOS_BP`](ALSO_IOS_BP) | All Business Premium-compatible artifacts | 15 |
| [`ALSO_IOS_E5`](ALSO_IOS_E5) | Cumulative: the same 15 artifacts; no additional E5-only source artifacts currently exist | 15 |

> [!WARNING]
> Choose **one** package per tenant. Do not combine packages. Review licensing, dependencies, assignments, and settings before import.

## 🌐 iOS/iPadOS coverage

| Area | Included content |
| --- | --- |
| Microsoft Defender | One application export, one managed-device app configuration, and one device configuration profile. |
| App protection | One app protection policy for iOS/iPadOS BYOD and corporate scenarios. |
| Compliance | Four compliance policies covering OS version, jailbreak/threat status, PIN/screen lock, and corporate MDE risk. |
| Conditional Access | Three policies, three exclusion groups, and `MigrationTable.json`. |

## 🚀 Getting started

1. Choose one package using the licensing guide above.
2. Read [General prerequisites](docs/public/general-prerequisites.md), [iOS/iPadOS prerequisites](docs/public/ios-ipados-prerequisites.md), [Defender for Cloud Apps](docs/public/defender-cloud-apps.md), and [Dependencies and special handling](docs/public/dependencies-and-errors.md).
3. Review the exact workload descriptions in [Policy and configuration descriptions](docs/public/policy-collections.md).
4. Follow [How to import](docs/public/how-to-import.md). **Always import Conditional Access policies in OFF mode** and use a controlled pilot.
