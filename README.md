# Project 4 — Password Spraying Detection and Investigation Using KQL

## Overview

This project demonstrates how Kusto Query Language (KQL) can be used to investigate failed sign-in activity and identify patterns that may indicate a password spraying attack.

Password spraying is an attack in which an attacker attempts a small number of commonly used passwords against multiple user accounts, aiming to avoid account lockout controls.

## Objectives

- Identify repeated failed sign-in attempts.
- Detect IP addresses attempting to access multiple user accounts.
- Investigate suspicious authentication patterns.
- Distinguish potential password spraying from normal authentication failures.
- Document detection logic and recommended SOC analyst actions.

## Tools and Technologies

- Kusto Query Language (KQL)
- Microsoft Sentinel / Microsoft Entra sign-in log concepts
- GitHub
- Sample or simulated authentication data, where applicable

## Detection Approach

The investigation focuses on:

1. Counting failed sign-in attempts by user and IP address.
2. Identifying IP addresses associated with multiple targeted accounts.
3. Examining activity within a defined time window.
4. Reviewing the results to determine whether additional investigation is warranted.

## Evidence

The `screenshots/` folder will contain evidence of the queries and their results where available. Any simulated data will be clearly labelled.

## Limitations

Failed sign-ins alone do not prove a password spraying attack. Legitimate users, misconfigured applications, and expired credentials can also cause repeated failures.

Detection results depend on the available log data, time range, and selected thresholds. This project does not claim a confirmed attack unless supporting evidence is available.

## Expected Learning Outcomes

- Practise KQL filtering, aggregation, and sorting.
- Understand authentication attack indicators.
- Develop a repeatable investigation workflow.
- Improve security analysis and technical documentation skills.

## Author

Owen Chiwenga

## Disclaimer

This is an educational cybersecurity project intended to demonstrate KQL detection and investigation techniques. No real user credentials are required or included.
