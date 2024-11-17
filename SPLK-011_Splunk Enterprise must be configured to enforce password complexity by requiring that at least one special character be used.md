## Splunk Enterprise must be configured to enforce password complexity by requiring that at least one special character be used.

# Information

Password complexity, or strength, is a measure of the effectiveness of a password in resisting attempts at guessing and brute-force attacks.

To meet password policy requirements, passwords need to be changed at specific policy-based intervals.

If the information system or application allows the user to consecutively reuse their password when that password has exceeded its defined lifetime, the end result is a password that is not changed as per policy requirements.

In most enterprise environments, this requirement is usually mitigated by a properly configured external authentication system, like LDAP. Splunk local authentication takes precedence over other forms of authentication and cannot be disabled. The mitigation settings in this requirement apply in the event a local account is created.

---

## Control

If the `authentication.conf` file does not exist, copy the file from `$SPLUNK_HOME/etc/system/default` to the `$SPLUNK_HOME/etc/system/local` directory.

Modify the following lines in the `authentication.conf` file under `[splunk_auth]`:

enablePasswordHistory = True  
passwordHistoryCount = 5  

---

## See Also

[Splunk Enterprise STIG Documentation (ZIP)](https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_Splunk_Enterprise_8-x_for_Linux_V2R1_STIG.zip)

---

## Item Details

- **Audit Name:** DISA STIG Splunk Enterprise 8.x for Linux v2r1 STIG OS
- **Category:** IDENTIFICATION AND AUTHENTICATION
- **References:**
  - 800-53|IA-5(1)(b)
  - CAT|III
  - CCI|CCI-004061
  - Rule-ID|SV-251688r992047_rule
  - STIG-ID|SPLK-CL-000410
  - Vuln-ID|V-251688
- **OS:** Unix

