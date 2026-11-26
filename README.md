Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
Start-Service sshd
Get-NetFirewallRule -Name OpenSSH-Server-In-TCP |
  Get-NetFirewallAddressFilter |
  Set-NetFirewallAddressFilter -RemoteAddress LocalSubnet
