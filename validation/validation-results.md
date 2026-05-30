# Atomic Red Team Validation Results
Lab: Windows Server 2022 (Azure D2s_v3) | Telemetry: Sysmon + PowerShell ScriptBlock Logging
Date: 2026-05-30

| Test | Technique | Atomic | Expected Event | Result |
|------|-----------|--------|----------------|--------|
| 1 | T1003.001 | LSASS dump via ProcDump | Sysmon EID 10 (ProcessAccess -> lsass.exe) | Detected |
| 2 | T1059.001 | PowerShell execution | PowerShell EID 4104 (ScriptBlock) | Detected |
| 3 | T1547.001 | Registry Run key persistence | Sysmon EID 13 (RegistryEvent) | Detected |
| 4 | T1562.001 | Impair defenses | Sysmon EID 1 (ProcessCreate) | Detected |
| 5 | T1055.001 | Process injection (remote thread) | Sysmon EID 8 (CreateRemoteThread) | Detected |
