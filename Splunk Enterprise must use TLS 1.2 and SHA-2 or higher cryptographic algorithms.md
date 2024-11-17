## Splunk Enterprise must use TLS 1.2 and SHA-2 or higher cryptographic algorithms.

# Information

Without cryptographic integrity protections, information can be altered by unauthorized users without detection.

To protect the integrity of the authenticator and authentication mechanism used for the cryptographic module used by the network device, the application, operating system, or protocol must be configured to use one of the following hash functions for hashing the password or other authenticator in accordance with SP 800-131Ar1:  
SHA-224, SHA-256, SHA-384, SHA-512, SHA-512/224, SHA-512/256, SHA3-224, SHA3-256, SHA3-384, and SHA3-512.

Splunk Enterprise, by default, is compliant with this requirement. However, since the settings can be overridden, the following checks and fixes are necessary.

---

## Control

Edit the following files in the `$SPLUNK_HOME/etc/system/local` folder:

### `inputs.conf`  
Applicable to the indexer (may be a separate machine in a distributed environment).  

Check for the following lines. If they do not exist, the settings are compliant. If they exist, they must match the settings below or be removed:  
- `sslVersions = tls1.2`  
- `ciphersuite = ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256`  
- `ecdhCurves = prime256v1, secp384r1, secp521r1`  

### `outputs.conf`  
Applicable to the forwarder (always a separate machine in the environment).  

Check for the following lines. If they do not exist, the settings are compliant. If they exist, they must match the settings below or be removed:  
- `sslVersions = tls1.2`  
- `ciphersuite = ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256`  
- `ecdhCurves = prime256v1, secp384r1, secp521r1`  

### `server.conf`  
Check for the following lines. If they do not exist, the settings are compliant. If they exist, they must match the settings below or be removed:  
- `sslVersions = tls1.2`  
- `sslVersionsForClient = tls1.2`  
- `ciphersuite = ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:AES256-GCM-SHA384:AES128-GCM-SHA256:AES128-SHA256`  
- `ecdhCurves = prime256v1, secp384r1, secp521r1`  

### `web.conf`  
Applicable to the search head or deployment server (may be a separate machine in a distributed environment).  

Check for the following lines. If they do not exist, the settings are compliant. If they exist, they must match the settings below or be removed:  
- `sslVersions = tls1.2`  
- `ciphersuite = ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256`  
- `ecdhCurves = prime256v1, secp384r1, secp521r1`  

### `/etc/openldap/ldap.conf`  

Check for the following lines, and set them to match the settings below:  
- `TLS_PROTOCOL_MIN 3.3`  
- `TLS_CIPHER_SUITE ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256`  

**Note:** Splunk Enterprise must operate in FIPS mode to limit the algorithms allowed.

---

## See Also

[Splunk Enterprise STIG Documentation (ZIP)](https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_Splunk_Enterprise_8-x_for_Linux_V2R1_STIG.zip)

---

## Item Details

- **Audit Name:** DISA STIG Splunk Enterprise 8.x for Linux v2r1 STIG OS
- **Category:** IDENTIFICATION AND AUTHENTICATION
- **References:**
  - 800-53|IA-7
  - CAT|I
  - CCI|CCI-000803
  - Rule-ID|SV-251689r961896_rule
  - STIG-ID|SPLK-CL-000430
  - Vuln-ID|V-251689
- **OS:** Unix

