---
layout: doc
---
# Smart Tools Agent and connectivity requirements

> **Important:**
>
> This article includes references to Smart Scale which will reach End of Life on **May 31, 2019**. For more information about Smart Scale deprecation, see the following articles:
>
> *  [What's New in Smart Tools](https://docs.citrix.com/en-us/smart-tools/whats-new.html)
> *  [Deprecation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/whats-new/removed-features.html) in Virtual Apps and Desktops

The Smart Tools Agent is a lightweight software package that coordinates [Smart Check](/en-us/smart-tools/system-requirements/check-requirements.html) and [Smart Scale](/en-us/smart-tools/system-requirements/scale-requirements.html) activities, collects metrics, and transmits logs. The agent enables Smart Tools to communicate with machines in a Virtual Apps and Desktops Site.

## Smart Tools Agent requirements

The Smart Tools Agent is installed on one or more Delivery Controllers with one of the following operating systems:

*  Windows Server 2012 R2
*  Windows Server 2016

Delivery Controllers hosting the Smart Tools Agent must meet the following requirements:

*  Supports PowerShell 3.0 (minimum).
*  No previous versions of the Smart Tools Agents are installed.

> **Important**:
>
> The Smart Tools Agent is supported for use only on Delivery Controllers in an on-premises Virtual Apps and Desktops deployment. The agent is not supported for use on machines that host other Citrix product or cloud service components, such as Cloud Connectors.

For more information about installing the Smart Tools Agent, see [Add a Site to Smart Tools](/en-us/smart-tools/install-configure/add-site.html).

## Port requirements

The Citrix Smart Tools Agent requires access over port 443 (outbound HTTPS) across the Internet to the following domains:

*  `https://*.citrixworkspacesapi.net`
*  `https://*.cloud.com`
*  cloudfront.net
*  smart.cloud.com
*  smart-agent.cloud.com
*  smart-eu.cloud.com
*  rttf.citrix.com
*  manage-disc.citrix.com
*  manage-monlb.citrix.com
*  smart-ap-s.cloud.com
*  ctxsym.citrix.com

Alternatively, you can allow access to the following public IP addresses:

*  162.221.156.0/24 subnet (or 162.221.156.65 to 162.221.156.74)
*  34.192.194.243
*  34.199.85.237
*  52.44.224.63
*  13.82.89.73
*  40.87.65.119

**Important:** Citrix recommends using the domains listed above as public IPs are subject to change. If you choose to use the public IP addresses instead, visit [status.cloud.com](https://status.cloud.com) and subscribe to Citrix Cloud notifications to stay informed of future updates to these IP addresses.

Ensure the machines hosting the Smart Tools Agent are able to resolve external DNS names. Communication between your server and Citrix Smart Tools occurs over port 443 (outbound HTTPS) only.

## Firewall requirements

Ensure that the firewall allows SSL traffic from your servers to the Citrix Smart Tools domains over port 443 (outbound HTTPS).

## Proxy requirements

If your resource location is behind a proxy, the Smart Tools Agent requires a pass-through connection to the proxy server. For more information about configuring proxy settings for the Smart Tools Agent, see [Use the Citrix Smart Tools Agent behind a proxy](/en-us/smart-tools/smart-tools-agent/use-agent-with-proxy.html).

> **Note**:
>
> The agent does not work with HTTPS proxy content inspection on the SSL session. If the proxy has content inspection, set up a rule on the proxy to pass traffic from the servers where the agent is installed.