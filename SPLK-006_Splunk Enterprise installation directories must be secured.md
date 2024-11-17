## Splunk Enterprise installation directories must be secured

# Information

If audit data were to become compromised, then competent forensic analysis and discovery of the true source of potentially malicious system activity is difficult if not impossible to achieve. In addition, access to audit records provides information an attacker could potentially use to his or her advantage.

To ensure the veracity of audit data, the information system and/or the application must protect audit information from any and all unauthorized access. This includes read, write, and copy access.

This requirement can be achieved through multiple methods which will depend upon system architecture and design. Commonly employed methods for protecting audit information include least privilege permissions as well as restricting the location and number of log file repositories.

Additionally, applications with user interfaces to audit records should not allow for the unfettered manipulation of or access to those records via the application. If the application provides access to the audit data, the application becomes accountable for ensuring audit information is protected from unauthorized access.

Audit information includes all information (e.g., audit records, audit settings, and audit reports) needed to successfully audit information system activity.

**Satisfies:** SRG-APP-000118-AU-000100, SRG-APP-000119-AU-000110, SRG-APP-000120-AU-000120, SRG-APP-000121-AU-000130, SRG-APP-000122-AU-000140, SRG-APP-000123-AU-000150

---

## Control

Only the `splunk` and `root` users should have access to the Splunk Enterprise installation directories.

```bash
chown splunk user $SPLUNK_HOME and $SPLUNK_ETC
chgrp splunk user $SPLUNK_HOME and $SPLUNK_ETC
chmod 700 $SPLUNK_HOME and $SPLUNK_ETC
```

---

## See Also

[Splunk Enterprise STIG Documentation (ZIP)](https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_Splunk_Enterprise_8-x_for_Linux_V2R1_STIG.zip)

---

## Item Details

- **Audit Name:** DISA STIG Splunk Enterprise 8.x for Linux v2r1 STIG OS
- **Category:** AUDIT AND ACCOUNTABILITY
- **References:**
  - 800-53|AU-12(3)
  - CAT|III
  - CCI|CCI-001914
  - Rule-ID|SV-251672r960930_rule
  - STIG-ID|SPLK-CL-000120
  - Vuln-ID|V-251672
- **OS:** Unix
