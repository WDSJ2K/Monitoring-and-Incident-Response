## Title: Configuration Lost After Device Reload Due to Unsaved Running Configuration

## Summary
Router configuration changes (hostname and static host entries) existed in the running configuration but were not present in the startup configuration, resulting in configuration loss after a device reload.

## Detection
The issue was identified during an IOS configuration management walkthrough when the startup configuration was reviewed and found to be missing user-configured settings.

## Impact
After a reload, the router reverted to default settings, causing loss of the configured hostname and local host mappings. No production impact occurred, as this was a lab environment.

## Troubleshooting
Reviewed the running configuration to confirm user-defined settings were active.
Checked the startup configuration and observed that it did not contain the same entries.
Determined that the running configuration had not been saved to NVRAM prior to reload.

## Resolution
Copied the running configuration to the startup configuration to ensure persistence across reloads.

## Validation
Reloaded the device and verified that the hostname and static host entries were present after startup.

## Evidence
-[001-show-running-config.txt](Monitoring-and-Incident-Response/Evidence/001-show-running-config.txt)

-[001-show-startup-config.txt](Monitoring-and-Incident-Response/Evidence/001-show-startup-config.txt)
