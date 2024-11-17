# Splunk Enterprise must automatically lock the account until the locked account is released by an administrator when three unsuccessful login attempts in 15 minutes are exceeded.
# Information

By limiting the number of failed login attempts, the risk of unauthorized system access via user password guessing, otherwise known as brute forcing, is reduced. Limits are imposed by locking the account.

---

## Control

If the `authentication.conf` file does not exist, copy the file from `$SPLUNK_HOME/etc/system/default` to the `$SPLUNK_HOME/etc/system/local` directory.

Modify the following line in the `authentication.conf` file under `[splunk_auth]`:

lockoutUsers = True or 1  

---

## See Also

[Splunk Enterprise STIG Documentation (ZIP)](https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_Splunk_Enterprise_8-x_for_Linux_V2R1_STIG.zip)

---

## Item Details

- **Audit Name:** DISA STIG Splunk Enterprise 8.x for Linux v2r1 STIG OS
- **Category:** ACCESS CONTROL
- **References:**
  - 800-53|AC-7b.
  - CAT|II
  - CCI|CCI-002238
  - Rule-ID|SV-251660r961368_rule
  - STIG-ID|SPLK-CL-000070
  - Vuln-ID|V-251660
- **OS:** Unix
