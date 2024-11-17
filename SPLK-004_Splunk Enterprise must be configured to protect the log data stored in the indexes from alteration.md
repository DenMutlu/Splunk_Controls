## Splunk Enterprise must be configured to protect the log data stored in the indexes from alteration

# Information

Without non-repudiation, it is impossible to positively attribute an action to an individual (or process acting on behalf of an individual).

The records stored by Splunk Enterprise must be protected against alteration. A hash is one way of performing this function. The server must not allow the removal of identifiers or date/time, or it must severely restrict the ability to do so.

---

## Control

If the `indexes.conf` file does not exist, copy the file from `$SPLUNK_HOME/etc/system/default` to the `$SPLUNK_HOME/etc/system/local` directory.

Modify the following line in the `indexes.conf` file under each index:

enableDataIntegrityControl = 1 or True  

---

## See Also

[Splunk Enterprise STIG Documentation (ZIP)](https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_Splunk_Enterprise_8-x_for_Linux_V2R1_STIG.zip)

---

## Item Details

- **Audit Name:** DISA STIG Splunk Enterprise 8.x for Linux v2r1 STIG OS
- **Category:** AUDIT AND ACCOUNTABILITY
- **References:**
  - 800-53|AU-10
  - CAT|II
  - CCI|CCI-000166
  - Rule-ID|SV-251662r960864_rule
  - STIG-ID|SPLK-CL-000090
  - Vuln-ID|V-251662
- **OS:** Unix
