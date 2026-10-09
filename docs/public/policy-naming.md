# 📖 Policy naming

[Public documentation](README.md) | [Repository preview](../../README.preview.md)

The existing iOS README documents this descriptive convention:

```text
<ALSO>-<ImpactLevel>-<MinimumLicense>-<BaselineLevel>-<Version>-<OS>-<Main Category>-<Sub Category>-<Settings>-<Assignment>
```

This is a reading guide, **not a claim that every checked-in export follows the full format**. The actual app protection, app configuration, and VPN names put the category before a bracketed platform/ownership label and omit a human-readable version. Compliance and CA use different formats.

## 🧩 Naming components

| Component | Meaning | Examples / caveats |
| --- | --- | --- |
| `ALSO` | Template provider | Descriptive prefix, not a tenant identifier. |
| Impact | Expected implementation impact | `LI` low, `MI` medium, `HI` high; full-style exports here use `MI`. Test actual user impact. |
| MinimumLicense | Source license classification | `BP` means Microsoft 365 Business Premium in the existing README. Verify current entitlement per setting. |
| BaselineLevel | Baseline label | `Basic` appears in full-style names; there are no Basic/Adv build packages in this repository. |
| Version | Human-readable policy version, when present | The documented convention allows `v1.0`; current full-style names omit it. Graph metadata versions are not this name component. |
| OS / ownership | Target platform and intended scenario | Display names use `iOS/iPadOS`, with `BYOD`, `Corp`, or `BYOD and Corp`; filenames use `iOSiPadOS`. |
| Category / settings | Resource area and purpose | App Protection, App Configuration, DeviceConfig/VPN, Compliance. |
| Assignment | Intended scope suffix, when present | `D` device, `U` user. A suffix does not create or prove an assignment. |

## 🗂️ Actual formats

| Resource | Observed pattern / example |
| --- | --- |
| App protection | `ALSO- MI- BP- Basic -App Protection- [iOS/iPadOS - BYOD and Corp] - Microsoft 365 apps` |
| App configuration | `ALSO- MI- BP- Basic - App Configuration- [iOS/iPadOS - Corp] - Defender Configuration - D` |
| VPN configuration | `ALSO- MI- BP- Basic - DeviceConfig- VPN- [iOS/iPadOS -Corp]- Auto Enrollment to MDE - D` |
| Compliance | `ALSO - Compliance - iOS/iPadOS - <BYOD or Corp> - <check> - D` |
| Conditional Access | `BP-ALSO-CA<number>-<audience>-<apps>-<platform>-...-Grant-<control>`; current identifiers are CA005, CA110, CA210. |

Names retain inconsistent spacing and existing spelling. Exports have not been renamed or normalized for this preview. See [Naming exceptions](short-name-exceptions.md) before interpreting names as scope or enforcement.

> [!NOTE]
> Settings, conditions, references, and actual target assignments take precedence over names. Use [File structure](file-structure.md) and inspect the selected JSON before deployment.
