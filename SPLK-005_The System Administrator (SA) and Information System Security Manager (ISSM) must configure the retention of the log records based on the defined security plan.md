## The System Administrator (SA) and Information System Security Manager (ISSM) must configure the retention of the log records based on the defined security plan

# Information

If authorized individuals do not have the ability to modify auditing parameters in response to a changing threat environment, the organization may not be able to respond effectively, and important forensic information may be lost.

The organization must define and document log retention requirements for each device and host and then configure Splunk Enterprise to comply with the required retention period.

This requirement enables organizations to extend or limit auditing as necessary to meet organizational requirements. Auditing that is limited to conserve information system resources may be extended to address certain threat situations.

---

## Control

Edit the following file in the Splunk installation folder:

`$SPLUNK_HOME/etc/system/local/indexes.conf`

Set `frozenTimePeriodInSecs` to the defined retention period for each index location.

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
  - Rule-ID|SV-251665r960891_rule
  - STIG-ID|SPLK-CL-000120
  - Vuln-ID|V-251665
- **OS:** Unix
