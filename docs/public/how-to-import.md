# 📥 How to import

[Public documentation](README.md) | [Repository preview](../../README.preview.md)

Complete [General prerequisites](general-prerequisites.md) and [iOS/iPadOS prerequisites](ios-ipados-prerequisites.md). Select only the resources needed for the intended scenario using [File structure](file-structure.md).

Use the [Micke M Intune Management Tool](https://github.com/Micke-K/IntuneManagement) to import these exports. Follow the documentation for the version you choose; UI labels and authentication can differ. The Windows version 3 WPF workflow is described below; do not assume its `start.cmd` launcher runs on macOS. The tool's version 4 branch has separate cross-platform instructions.

## Download and sign in

1. Download this repository through **Code > Download ZIP**, or clone it. Extract to a short path such as `C:\Intune\iOS`. Long policy filenames can exceed Windows extraction/path limits; use a long-path-capable tool if needed and verify all **15 JSON files** are present. OneDrive does not itself remove path limits, and is not required for import.
2. Download/extract the Intune Management Tool. Review its source, prerequisites, and authentication permissions. On Windows with the version 3 tool, launch `start.cmd` from its folder.
3. Use the sign-in icon to authenticate to the intended tenant. Confirm the tenant before any write operation.
4. If API consent is needed, have an authorized administrator review the requested permissions and approve them through the organization's process; use **Request Consent** if appropriate to that tool version. Do not grant broad consent blindly.
5. Back up relevant target resources and inventory existing policies/apps/groups to avoid duplicates. The tool's default **Always import** behavior can create new objects; Replace/Update have different risks and must be tested separately.

## Import selected workloads

| Step | Resource selection | Safety / dependency check |
| --- | --- | --- |
| 1 | CA exclusion groups and reference mapping, if importing CA | Keep `ALSO_IOS_CA_POLICIES/Groups` and `MigrationTable.json` available to the tool. Use its supported dependency/migration workflow to resolve source IDs to target groups, or map to reviewed existing groups. |
| 2 | Defender app, for corporate onboarding | Import/select Microsoft Defender in the target tenant first. The Store app export does not supply volume-purchase licensing or a required-install assignment. |
| 3 | Managed-device Defender app configuration and VPN profile | Resolve `targetedMobileApps` to the correct target app. Adapt the onboarding design to supervision, enrollment, and user affinity; see [iOS/iPadOS prerequisites](ios-ipados-prerequisites.md). |
| 4 | App protection and selected compliance policies | Review supported apps, data controls, compliance actions and thresholds. Device compliance is for enrolled devices, not MAM-only BYOD. |
| 5 | Conditional Access policies, **Off** | Confirm `state=disabled` in the target tenant, then validate all users/roles/apps/platforms, device filters, and mapped exclusion groups. |

In the Windows tool UI, select **Bulk > Import**, use the appropriate policy-set folder, and select only its intended workload types. Where available, enable **Add Object name to path** for workload-folder discovery. Inspect the actual selection rather than selecting the repository root. Leave **Import assignments** unchecked.

`MigrationTable.json` is metadata for resolving references, **not a policy to upload**. Its tenant information describes the source environment, not your target tenant. Leaving assignment import unchecked does not remove CA's built-in user/role/app conditions: review those separately. Importing an exclusion group does not populate or verify emergency-access membership.

> [!WARNING]
> **Always import Conditional Access in Off mode.** All three checked-in policies are disabled, but verify the result rather than relying on the export. CA includes Android, and CA210 includes all users. CA110/CA210 can deny access to unenrolled BYOD even when CA005 app protection succeeds.

## Review, pilot, and roll out

1. Review import results and command-window output for errors. Inspect each resource in Intune/Entra; check settings, target app references, tenant/group mappings, scope tags, and duplicate objects. Stop if references are unresolved.
2. Verify emergency-access accounts, exclusion-group membership, and recovery access in the target tenant. Confirm combined CA behavior with **What If**, sign-in logs, and an approved report-only phase; keep policies Off until those prerequisites are met.
3. Assign app protection to intended pilot users; assign device policies to the reviewed enrolled-device population. Set Defender deployment to **Required** for the corporate pilot and review supported installation/removal controls separately.
4. Validate work-account app protection, PIN/data-sharing/printing/screen-capture behavior on supported apps, compliance checks and zero-grace actions, Defender onboarding/protection/risk reporting, and successful permitted sign-ins. Include an unenrolled BYOD test if that scenario is intended.
5. Check VPN compatibility, user interaction, privacy, and noncompliance recovery. Only then move CA from report-only to approved staged enforcement and expand assignments.

Report-only results are not proof that app protection is enforced: Microsoft's guidance notes that this grant can show report-only failure before enforcement. Validate actual protected-app behavior in a controlled, narrowly scoped enforcement pilot as well.

Do not re-import repeatedly to repair errors without checking for duplicate objects. Use [Reporting issues](reporting-issues.md) for reproducible repository or documentation problems.
