Sigma Rule Writing Guide: [My Method]
[Step 1:] Define the Metadata
Every rule starts with metadata that explains its purpose and ownership. Define a clear, descriptive title, add your name as the author, assign a unique rule ID, and set the status (experimental, stable). The description should clarify what the rule is catching and why it matters. Include links to MITRE ATT&CK or threat research in the references.

[Step 2:] Identify the Log Source
Specify where the detection logic will apply. You define the product (like Windows, Linux, or any) and the service (like Security logs, PowerShell logs, or auditd). This tells the Sigma engine what logs to parse.

[Step 3:] Write the Detection Logic
This is the heart of the rule. Define selection patterns using fields like EventID, process names, or command lines. Use operators like contains, startswith, or endswith to pinpoint activity. Wrap this up with a condition line that dictates when the rule triggers.

[Step 4:] Document False Positives
Think ahead—what legitimate activities might trigger this rule? List them in falsepositives. This helps avoid alert fatigue and informs responders what to watch for.

[Step 5:] Set Severity Level
Assign a level—high, medium, or low. This helps triage efforts when alerts fire. If it’s indicative of immediate compromise, it’s high. If it’s suspicious but not definitive, it’s medium or low.

[Step 6:] Map to MITRE ATT&CK
Tag every rule with the relevant MITRE TTP. For example, if it’s a PowerShell execution rule, you’d tag attack.execution and attack.t1059.001. This makes threat hunting and reporting easier.


