# 📖 Policy and configuration descriptions

[Documentation index](README.md) | [Repository README](../../README.md)

The authored descriptions and warnings follow verbatim.

## What's included in ALSO_IOS_MDE_AUTO_ONBOARDING?

This policy set is designed to automate the onboarding of Corporate Owned iOS and iPadOS devices to Microsoft Defender for Business and Microsoft Defender for Endpoint. 

This folder contains:


| Component | Description |
|-----------|-------------|
| Application | 1 Application: Microsoft Defender: Security for iOS and iPadOS | Auto installs on device once device are enrolled to Intune. Set as Required and Uninstall is not allowed. 
| Device Configuration Settings | 1 policy template: Auto onboarding to MDE policy template | Auto onboards device to Defender once device are enrolled to Intune
| App Configuration Policy | 1 policy templates: Sets Real Time protection and Network Protection ON automatically. This policy also enables organizations to use MDCA - Microsoft Defender for Cloud Apps on those devices.  

> [!IMPORTANT]
> All these policy templates and the application are required to enable seamless automatic onboarding of iOS and iPadOS devices to Microsoft Defender for Endpoint when they are enrolled in Intune.
> ALSO doesn't recommend to push out Defender application to BYOD devices for privacy reasons.


## What's included in ALSO_IOS_APP_PROTECTION_POLICIES?

This policy set is designed to secure Microsoft 365 content on BYOD and Corp devices together with Conditional Access policies.

| Component | Description |
|-----------|-------------|
| App Protection Policy | 1 policy templates: Restricts copy paste to Non- Microsoft apps, print and screen capture of Microsoft app content, backup to iCloud and other cloud services etc.


## What's included in ALSO_IOS_COMPLIANCE_POLICIES?

This policy set is designed to require compliant device at sign in together with Conditional Access policies.  

| Component | Description |
|-----------|-------------|
| CompliancePolicies | 4 policy templates: Requires minimum 6 digit PIN and ecryption, requires minimum OS version iOS/iPadOS 17.0, disallows jailbroken devices. Requires Defender compliance for corp devices etc. 


## What's included in ALSO_IOS_CA_POLICIES?

This policy set is designed to require compliant device at sign in together with Conditional Access policies.  

| Component | Description |
|-----------|-------------|
| ConnditionalAccess | 3 policy templates: 2 of them requires compliant device at sign in for admins and internals and 3rd one requires app protection policies for all users. 
| Groups | 3 Exclude groups for Conditional Access policies incl Break Glass Account group
| MigrationTable.json | Migration table needed to import groups

> [!IMPORTANT]
> **Always import Conditional Access policies in OFF mode**:
