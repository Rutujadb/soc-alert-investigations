# Investigation 01 – Suspicious PowerShell Activity

## Alert Summary
- Alert Source: Windows PowerShell Operational Log
- Alert Type: Suspicious PowerShell Activity (Automated Detection)
- Trigger Time: <Timestamp from first relevant PowerShell event reviewed>
- Hostname: DESKTOP-VALRMMH$
- User: Rutuja Bhalerao

## Initial Triage
State that PowerShell activity was reviewed due to alert
Mention scope: host-level PowerShell execution + auth/process events
State no immediate high-risk indicators observed

## Evidence Collected
- logs/powershell-operational.evtx
- logs/security.evtx
- artifacts/powershell-4104-scriptblock-last200.txt
- timeline/powershell-operational-last200.txt
- timeline/security-auth-proc-last500.txt

## Key Event IDs to Review
- PowerShell: 4104 (ScriptBlock Logging)
- Security: 4624, 4625, 4688

## Investigation Timeline
- T0 – Alert triggered: PowerShell activity flagged by automated monitoring
- T1 – Logs collected: PowerShell Operational, Security, ScriptBlock logs exported
- T2 – Events correlated: Reviewed authentication, process creation, and script execution
- T3 – Conclusion reached: No malicious indicators observed in reviewed timeframe

## Findings
ScriptBlock logging (4104) enabled and reviewed
No encoded commands, download cradles, LOLBins, or Defender tampering observed
No corroborating suspicious process creation (4688) in reviewed window

## Conclusion
Verdict: False Positive / Benign Administrative Activity
Business impact: None observed
Confidence level: Medium–High (limited to last X events)

## Recommended Actions
No containment required
Recommend continued ScriptBlock logging
Suggest alert tuning to reduce noise
