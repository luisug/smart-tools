---
layout: doc
---
# Use the Citrix Smart Tools Agent behind a proxy

If your Virtual Apps and Desktops Site is behind a proxy, the Smart Tools Agent requires a pass-through connection to the proxy server. This article describes how to configure proxy settings needed to enable the agent to communicate with Smart Tools.

For firewall settings, see [Smart Tools Agent and connectivity requirements](/en-us/smart-tools/system-requirements/connectivity-requirements.html).

## Required environment variables

The Smart Tools Agent acquires proxy settings from environment variables configured on the Windows machine that hosts the agent. The Smart Tools Agent uses the following environment variables to recognize the proxy server using basic authentication (username and password). These variables are not case sensitive.

*  **HTTPS_PROXY=proxyserver_ip_address:port** - For **port**, enter the port your proxy is configured to use for communication to the Internet. Examples: 124.26.30.4:443; 164.224.136.1:80
*  **HTTPS_PROXY_USERNAME=my_username** - If your proxy is configured to require connection credentials, configure this variable. If your proxy is configured for anonymous access, configuring this variable is not necessary.
*  **HTTPS_PROXY_PASSWORD=my_password** - If your proxy is configured to require connection credentials, configure this variable. If your proxy is configured for anonymous access, configuring this variable is not necessary.

If your proxy server does not have authentication, the Smart Tools Agent will pass traffic over HTTPS through your proxy to the public Internet. If you are using authentication other than basic (e.g., NTLM), the agent traffic will fail authentication.

> **Note**:
>
> The agent will not work with HTTPS proxy content inspection on the SSL session. If the proxy has content inspection, then you must set up a rule on the proxy to pass through traffic from servers where the agent is installed.

## To set environment variables on Windows machines

To ensure the Smart Tools Agent can recognize the proxy server, you must configure the proxy settings as system [environment variables](#required-environment-variables) on the machine hosting the agent. By default, the agent does not look in IE global settings for proxy setting information. If no environment variables have been set, then the agent assumes there is no proxy configuration.

![Windows Environment Variables dialog with System Variables pane highlighted](/en-us/smart-tools/media/win-system-vars-highlighted.png)

To add system variables, perform the following actions:

1.  Click **Start > Control Panel > System and Security > System > Advanced system settings**.
1.  On the **Advanced** tab, click **Environment Variables**.
1.  In the **System variables** pane, click **New** to add each variable.