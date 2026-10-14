# Investigation Report — Password Spraying Detection Using KQL

## 1. Overview

This project demonstrates a KQL-based approach to investigating failed authentication attempts and identifying patterns that may indicate password spraying.

Password spraying involves attempting a small number of passwords against multiple accounts. The objective is to identify suspicious authentication patterns for further investigation.

## 2. Investigation Objectives

- Review recent failed sign-in events.
- Count failures by user account and source IP address.
- Identify IP addresses associated with multiple targeted accounts.
- Identify accounts receiving failures from multiple source IP addresses.
- Recommend appropriate investigation steps.

## 3. Tools and Data

- Kusto Query Language (KQL)
- Microsoft Entra sign-in log concepts
- GitHub for query and report documentation

The queries use the `SigninLogs` table, which is available in appropriately configured Microsoft Sentinel or Log Analytics environments when the relevant sign-in data is collected.

## 4. Detection Methodology

### Query 1 — Recent Failed Sign-ins

Reviews recent unsuccessful authentication events and displays relevant fields, including timestamp, user, source IP, result code, and application.

### Query 2 — Failed Attempts by User and IP

Groups failed sign-ins by user account and source IP to help identify repeated authentication failures.

### Query 3 — IP Addresses Targeting Multiple Accounts

Counts failed attempts and distinct targeted accounts for each IP address. The example threshold of five accounts is an initial investigation filter, not a universal definition of password spraying.

### Query 4 — Accounts Receiving Attempts from Multiple IPs

Counts failed attempts and distinct source IP addresses associated with each user. This may help identify distributed attempts or legitimate causes that require review.

## 5. Analyst Investigation Steps

For any suspicious results:

1. Confirm the time range and the available log coverage.
2. Review the authentication result codes and targeted accounts.
3. Check whether the source IP address is expected or associated with legitimate organizational activity.
4. Look for successful sign-ins following the failures.
5. Correlate with other available identity, endpoint, and incident evidence.
6. Follow organizational procedures before taking containment actions.

## 6. Limitations

- The queries require the appropriate `SigninLogs` table and column names.
- Failed sign-ins alone do not confirm malicious activity.
- Shared networks, VPNs, misconfigured applications, and legitimate users may produce similar patterns.
- Thresholds should be tuned to the organization's normal authentication activity.
- Results must be validated against actual or clearly labelled simulated data.

## 7. Conclusion

This project demonstrates how KQL aggregation, filtering, distinct counts, and sorting can support an initial authentication investigation. The queries identify patterns for analyst review; they do not independently prove that a password spraying attack occurred.

## Author

Owen Chiwenga

## Disclaimer

Educational cybersecurity project. No real credentials are required or included. Detection results should not be described as confirmed incidents without supporting evidence.
