# 📖 Policy naming

[Documentation index](README.md) | [Repository README](../../README.md)

The original file-structure and naming text follows verbatim. The active two-package layout is documented separately in [File structure](file-structure.md).

## 📂 File Structure

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

### License Tag Description

| Tag | Minimum Required License |
|:---:|--------------------------|
| **BP** | Microsoft 365 Business Premium |

---

## 📖 Naming Convention

All policy templates follow the naming format below:

```text
<ALSO>-<ImpactLevel>-<MinimumLicense>-<BaselineLevel>-<Version>-<OS>-<Main Category>-<Sub Category>-<Settings>-<Assignment>
```

### Example

```text
ALSO – LI – BP – Basic – v1.0– iOS/iPadOS BYOD or Corp –
```

---

## 🧩 Naming Components

| Component | Description |
|-----------|-------------|
| **ALSO** | Company providing the policy template to have a better control |
| **Impact** | Impact level of policy, low (LI), medium (MI) or high (HI) |
| **MinimumLicense** | Minimum Microsoft license required to use the policy |
| **BaselineLevel** | Baseline level of policy, Basic, Advanced |
| **Version** | Policy version, v1.0, v1.1 etc|
| **iOS/iPadOS** | Operating system |
| **MainCategory** | Name of main category, Device Configuration, Device Compliance etc|
| **SubCategory** | Name of sub category, MDE, AV, Disk etc|
| **Settings** | Short settings description |
| **Assignment** | Assignment scope- device (D) or user (U)|
