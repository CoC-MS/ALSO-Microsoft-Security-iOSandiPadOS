# 🚀 General prerequisites

[Public documentation](README.md) | [Repository preview](../../README.preview.md)

Check these items before importing any resources. Read the [security and usage notice](../../SECURITY) and prepare a documented rollback/recovery plan.

## 🔐 Licensing and services

The existing README identifies Microsoft 365 Business Premium as the baseline, and several names carry `BP`. Business Premium includes Intune, Microsoft Entra ID P1, and Defender for Business; other subscriptions or combinations may provide the required services. **A name is not a licensing check.** Confirm assigned user licenses, enabled services, and entitlement for every feature in the target tenant.

| Selected capability | Confirm before deployment |
| --- | --- |
| App protection and enrolled-device management | Appropriate Intune licensing, supported apps, and the chosen enrollment/MAM scenario. |
| Conditional Access | Microsoft Entra licensing for the selected controls, commonly Entra ID P1 for these CA scenarios, plus the services required by the grant control. |
| Defender onboarding and MDE-risk compliance | Defender for Business or appropriate Defender for Endpoint entitlement, licensed users, provisioned Defender service, and Intune integration. |
| Optional Defender for Cloud Apps integration | Separate licensing, supported-platform and service prerequisites; these exports do not configure or guarantee this integration. |

There are no cumulative BP/E3/E5 packages to choose from. Select individual resources by scenario using [File structure](file-structure.md).

## 🧰 Permissions and dependency review

Use least-privilege permissions for the selected operations; an import tool may require Graph permissions in addition to portal roles.

| Operation | Access to arrange |
| --- | --- |
| Import/configure Intune apps and profiles | Intune Administrator or appropriate scoped Intune RBAC roles, such as Application Manager and Policy and Profile Manager, with permissions for the selected resources. |
| Manage CA policies | Conditional Access Administrator or equivalent authorized role. |
| Create/manage exclusion groups | Appropriate group-management permissions; validate membership separately. |
| Configure Defender integration | Authorized Defender/security administration permissions for service settings and access to the relevant device groups. |
| Approve tool API consent | An administrator authorized to approve the requested permissions, following the organization's consent process. Do not assume every operator needs Global Administrator. |

Confirm the target tenant before importing. Review existing policies, source IDs, groups, app references, scope tags, exclusions, and enrollment-specific dependencies. Back up relevant target configurations using approved handling for tenant data. Do not bulk-import source assignments.

## 🧪 Deployment readiness

Define separate BYOD/MAM-only, enrolled BYOD, and corporate-managed populations. Prepare pilot users/devices, supported Microsoft apps, communications about PIN/data-sharing/privacy changes, and recovery access.

> [!WARNING]
> Keep CA policies **Off** until references and exclusions are verified. Requiring device compliance can block a MAM-only BYOD user even if app protection works. Evaluate the combined CA result, not each export in isolation. Do not enable all-user controls before confirming emergency access.

Plan how to observe app policy delivery, device compliance, Defender onboarding/risk signals, and sign-in results. The compliance exports have zero-grace noncompliance actions; review those values before a pilot.

Complete [iOS/iPadOS prerequisites](ios-ipados-prerequisites.md) before following [How to import](how-to-import.md).

## 📚 Microsoft sources

- [Microsoft Intune licensing](https://learn.microsoft.com/en-us/intune/intune-service/fundamentals/licenses)
- [Conditional Access overview and license requirements](https://learn.microsoft.com/en-us/entra/identity/conditional-access/overview)
- [Microsoft Defender for Business requirements](https://learn.microsoft.com/en-us/defender-business/mdb-requirements)
- [Deploy Defender on enrolled iOS devices](https://learn.microsoft.com/en-us/defender-endpoint/ios-install)
