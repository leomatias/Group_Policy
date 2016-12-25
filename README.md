# Group_Policy
A series of GPO templates<br>
<br>



# Blocking DNS Tunneling
### Computer Configuration -> Windows Settings -> Windows Firewall with Advanced Security -> Windows Firewall with Advanced Security...-> Outbound Rules
- Outbound Rules : Block Port 53 traffic to a specific IP. Be sure to select "Custom" when making the rule.
- Outbound Rules : Block port 53 traffic to all IPs except for one. For example, say we want to allow port 53 traffic to 174.7.6.100. We can block 0.0.0.1 - 174.7.6.99 and 174.7.6.101 - 255.255.255.255. Notice we didn't list 174.7.6.100 as an IP to block. Be sure to select "Custom" when making the rule.

# Enable WMI
### Computer Configuration -> Windows Settings -> Windows Firewall with Advanced Security -> Windows Firewall with Advanced Security...-> Outbound Rules
- Inbound Rules : Select the predefined rule for Windows Management Instrumentation and this will create three rules.

### Computer Configuration -> Administrative Templates -> Network Connections -> Windows Firewall -> Domain Profile (Do Standard Profile as well)
- Windows Firewall: Allow inbound remote administration exception : Enabled it and add the applicable IP(s).

# Allow ICMP
### Computer Configuration -> Administrative Templates -> Network Connections -> Windows Firewall -> Domain Profile (Do Standard Profile as well)
- Windows Firewall:Allow ICMP Exceptions : Once enabled, it will allow ICMP traffic.

# Allow SMB
### Computer Configuration -> Administrative Templates -> Network Connections -> Windows Firewall -> Domain Profile (Do Standard Profile as well)
- Windows Firewall:All inbound file and printer sharing exception : Enabled it and add the applicable IP(s). Once done, this will allow SMB. traffic from the specified IPs.

# Disable Command Prompt
### User Configuration -> Policies -> Administrative Templates -> System
- Prevent access to the command prompt : Enabled it and the command prompt will be disabled

# Enable PowerShell Execution Policy
### User Configuration -> Policies -> Administrative Template -> Windows PowerShell
- Turn on Script Execution : Enable it and select the applicable Execution Policy

# Firewall Settings
### Computer Configuration -> Windows Settings -> Windows Firewall with Advanced Security -> Windows Firewall with Advanced Security
- Enable Logging : Properties -> Logging
- Disable rules created locally to merge with GPO rules : Properties -> Settings -> Rule Merging

# Enable "Last Modified" Value
### Computer Configuration -> Preferences -> Windows Settings -> Registry
- NtfsDisableLastAccessUpdate : CHANGE this Value in HKLM\System\CurrentControlSet\Control\FileSystem to be "0"

# Disable VBS
### Computer Configuration -> Preferences -> Windows Settings -> Registry
- Enabled : CREATE this Value in HKLM\Software\Microsoft\Windows Script Host\Settings and set it (REG_DWORD) to "0"

# Enable Remote Registry
### Computer Configuration -> Policies -> Windows Settings -> Security Settings -> System Services
- RemoteRegistry : Define the Policy and set it to Automatic


