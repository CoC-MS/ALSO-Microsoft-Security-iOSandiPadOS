# 📂 File structure

[Documentation index](README.md) | [Repository README](../../README.md)

The repository exposes exactly two standalone top-level package folders:

```text
ALSO_IOS_BP/
├── ALSO_IOS_APP_PROTECTION_POLICIES/
├── ALSO_IOS_CA_POLICIES/
├── ALSO_IOS_COMPLIANCE_POLICIES/
└── ALSO_IOS_MDE_AUTO_ONBOARDING/

ALSO_IOS_E5/
├── ALSO_IOS_APP_PROTECTION_POLICIES/
├── ALSO_IOS_CA_POLICIES/
├── ALSO_IOS_COMPLIANCE_POLICIES/
└── ALSO_IOS_MDE_AUTO_ONBOARDING/
```

| Workload | BP | E5 |
| --- | ---: | ---: |
| App protection policies | 1 | 1 |
| Conditional Access policies | 3 | 3 |
| Conditional Access groups | 3 | 3 |
| Conditional Access migration table | 1 | 1 |
| Compliance policies | 4 | 4 |
| Defender application | 1 | 1 |
| Defender app configuration | 1 | 1 |
| Defender device configuration | 1 | 1 |
| **Total JSON files** | **15** | **15** |

All current artifacts are Business Premium-compatible according to the source README and filename markers. There are no E5-only source artifacts, so `ALSO_IOS_E5` is cumulative with identical membership.

The original file-structure wording is preserved in [Policy naming](policy-naming.md) and in the complete [authored README preservation copy](authored-readme.md).
