# ARTEX Host Guard

A defensive host-audit and hardening tool for devices you administer. Audit first, review the proposed change, then verify the result. The optional AI Connector is not required for hardening. This project does not bundle the original ARTEX toolkit.

## Validation: 1.2.0

The release test used a disposable Debian 13 QEMU guest with no external network. These results are for that test environment, not production systems.

| Check | Result |
| --- | --- |
| Local service audit | Detected the test TCP listener |
| Preview and cancel | Left the test file at `0644` |
| File hardening | `0644` → `0600`; file contents unchanged |
| Kernel protection | `0` → `1`; verified by readback; repeat apply made no change |
| Engine tests | 44 passed in the VM and passed again in a separate source check |
| Rust tests | 12 passed, plus one passing offline Connector smoke test |

The release test did not verify native macOS install, administrator prompts, Keychain, or real firewall changes. Windows and production networking were not tested in this VM.

Source and downloads are not published yet.
