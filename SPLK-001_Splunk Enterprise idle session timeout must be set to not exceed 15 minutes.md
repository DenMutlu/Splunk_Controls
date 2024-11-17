## Splunk Enterprise idle session timeout must be set to not exceed 15 minutes

# Information

Automatic session termination after a period of inactivity addresses the potential for a malicious actor to exploit the unattended session. Closing any unattended sessions reduces the attack surface to the application.

**Satisfies:** SRG-APP-000295-AU-000190, SRG-APP-000389-AU-000180

---

## Control

This configuration is performed on the machine used as a search head, which may be a separate machine in a distributed environment.

If the `web.conf` file does not exist, copy the file from `$SPLUNK_HOME/etc/system/default` to the `$SPLUNK_HOME/etc/system/local` directory.

Modify or add the following line in the `web.conf` file:

`tools.session.timeout = 15`

---

## See Also

[Splunk Enterprise STIG Documentation (ZIP)](https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_Splunk_Enterprise_8-x_for_Linux_V2R1_STIG.zip)

---

## Item Details

- **Audit Name:** DISA STIG Splunk Enterprise 8.x for Linux v2r1 STIG OS
- **Category:** ACCESS CONTROL
- **References:**
  - 800-53|AC-12
  - CAT|II
  - CCI|CCI-002361
  - CCI|CCI-004895
  - Rule-ID|SV-251657r992037_rule
  - STIG-ID|SPLK-CL-000010
  - Vuln-ID|V-251657
- **OS:** Unix
