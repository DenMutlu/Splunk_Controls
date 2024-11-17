## Splunk Enterprise must be configured to enforce password complexity by requiring that at least one special character be used.

# Information

The shorter the password, the lower the number of possible combinations that need to be tested before the password is compromised.

Password complexity, or strength, is a measure of the effectiveness of a password in resisting attempts at guessing and brute-force attacks. Password length is one factor of several that helps to determine strength and how long it takes to crack a password. The shorter the password, the lower the number of possible combinations that need to be tested before the password is compromised.

Use of more characters in a password helps to exponentially increase the time and/or resources required to compromise the password.

In most enterprise environments, this requirement is usually mitigated by a properly configured external authentication system, like LDAP. Splunk local authentication takes precedence over other forms of authentication and cannot be disabled. The mitigation settings in this requirement apply in the event a local account is created.

---

## Control

If the `authentication.conf` file does not exist, copy the file from `$SPLUNK_HOME/etc/system/default` to the `$SPLUNK_HOME/etc/system/local` directory.

Modify the following line in the `authentication.conf` file under `[splunk_auth]`:

minPasswordLength = 15 or more  

---

## See Also

[Splunk Enterprise STIG Documentation (ZIP)](https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_Splunk_Enterprise_8-x_for_Linux_V2R1_STIG.zip)

---

## Item Details

- **Audit Name:** DISA STIG Splunk Enterprise 8.x for Linux v2r1 STIG OS
- **Category:** IDENTIFICATION AND AUTHENTICATION
- **References:**
  - 800-53|IA-5(1)(a)
  - CAT|III
  - CCI|CCI-004066
  - Rule-ID|SV-251684r992044_rule
  - STIG-ID|SPLK-CL-000370
  - Vuln-ID|V-251684
- **OS:** Unix
