# Information

By limiting the number of failed login attempts, the risk of unauthorized system access via user password guessing, otherwise known as brute forcing, is reduced. Limits are imposed by locking the account.

In most enterprise environments, this requirement is usually mitigated by a properly configured external authentication system, like LDAP. Splunk local authentication takes precedence over other forms of authentication. The mitigation settings in this requirement apply in the event a local account is created.

---

## Control

If the `authentication.conf` file does not exist, copy the file from `$SPLUNK_HOME/etc/system/default` to the `$SPLUNK_HOME/etc/system/local` directory.

Modify the following lines in the `authentication.conf` file under `[splunk_auth]`:

lockoutAttempts = 3  
lockoutThresholdMins = 15  

---

## See Also

[Splunk Enterprise STIG Documentation (ZIP)](https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_Splunk_Enterprise_8-x_for_Linux_V2R1_STIG.zip)

---

## Item Details

- **Audit Name:** DISA STIG Splunk Enterprise 8.x for Linux v2r1 STIG OS
- **Category:** ACCESS CONTROL
- **References:**
  - 800-53|AC-7a.
  - CAT|II
  - CCI|CCI-000044
  - Rule-ID|SV-251659r960840_rule
  - STIG-ID|SPLK-CL-000060
  - Vuln-ID|V-251659
- **OS:** Unix
