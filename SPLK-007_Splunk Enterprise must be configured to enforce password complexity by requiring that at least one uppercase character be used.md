## Splunk Enterprise must be configured to enforce password complexity by requiring that at least one uppercase character be used.

# Information

Use of a complex password helps to increase the time and resources required to compromise the password. Password complexity, or strength, is a measure of the effectiveness of a password in resisting attempts at guessing and brute-force attacks.

Password complexity is one factor of several that determine how long it takes to crack a password. The more complex the password, the greater the number of possible combinations that need to be tested before the password is compromised.

In most enterprise environments, this requirement is usually mitigated by a properly configured external authentication system, like LDAP. Splunk local authentication takes precedence over other forms of authentication and cannot be disabled. The mitigation settings in this requirement apply in the event a local account is created.

---

## Control

If the `authentication.conf` file does not exist, copy the file from `$SPLUNK_HOME/etc/system/default` to the `$SPLUNK_HOME/etc/system/local` directory.

Modify the following line in the `authentication.conf` file under `[splunk_auth]`:

minPasswordUppercase = 1  

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
  - Rule-ID|SV-251681r992041_rule
  - STIG-ID|SPLK-CL-000340
  - Vuln-ID|V-251681
- **OS:** Unix
