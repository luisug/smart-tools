---
layout: doc
---
# Troubleshoot Citrix Checks

This topic provides troubleshooting tips for issues that might occur when running Citrix Checks.

## License Server Checks fail due to unknown exception

When running License Server Checks, the checks fail with the following exception:

"The License Server Check failed to run. Verify the Basic authentication role service is installed and ensure the computer appears on the Trusted Hosts list."

This issue occurs because the WinRM client can't process the request. You can use default authentication with an IP address according the following conditions:

*  The transport protocol is HTTPS or the destination is on the Trusted Hosts list.
*  Explicit credentials are provided.

### Verify requirements for License Server Checks

In addition to the [system requirements for targeted machines](/en-us/smart-tools/checks/about-health-checks.html#system-requirements-for-targeted-machines), ensure you have met the following requirements for using License Server Checks:

Ensure you have met the requirements for running License Server Checks:

*  The License Server is joined to a domain. Smart Tools doesn’t support License Servers that are not joined to a domain.
*  The License Server FQDN is configured in Citrix Studio.
*  The certificate installed in the trust root is issued with the FQDN of the License Server
*  If you are switching to a new License Server, ensure all alerts for the previous License Server have been resolved.

### Install the Basic authentication role service

To install the Basic authentication role service, follow the steps as described in [https://docs.microsoft.com/en-us/iis/configuration/system.webserver/security/authentication/basicauthentication](https://docs.microsoft.com/en-us/iis/configuration/system.webserver/security/authentication/basicauthentication)  on the Microsoft Docs web site.

### Add the License Server to the Trusted Hosts list

To add your License Server to the Trusted Hosts list, you can use either the computer name or the IP address of the License Server.

To add a computer name to the Trusted Hosts list:

1.  Start Windows PowerShell with elevated privileges.
2.  At the command prompt, type the following command:

    `set-item wsman:\localhost\Client\TrustedHosts -value <ComputerName>[,<ComputerName>]`

    where `<ComputerName>` has the format `<Computer>.<Domain>.<Company>.<top-level-domain>`.

Example:

```
set-item wsman:\localhost\Client\TrustedHosts -value Server01.Domain01.Example.com

```

To add the IP address of your License Server to the Trusted Hosts list:

1.  Start Windows PowerShell with elevated privileges.
1.  At the command prompt, type the following command:

    `set-item wsman:\localhost\Client\TrustedHosts -value 0.0.0.0, [0:0:0:0:0:0:0:0]`

    where `0.0.0.0` is an IP address in IPv4 format and `[0:0:0:0:0:0:0:0]` is an IP address in IPv6 format.

Examples:

```
set-item wsman:\localhost\Client\TrustedHosts -value 166.20.198.117

set-item wsman:\localhost\Client\TrustedHosts -value 0:0:0:0:0:ffff:a614:c675

```