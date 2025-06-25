# Sysmon-Threat-hunting-Detect-Suspicious-Activity
I'll be using sysmon in a VM to detect suspicious activity
## GOAL
 To use Sysmon on a windows VM to detect suspecious activity like process injection, network connections or exection of unsigned binaries 
## STEP ONE 
1. Download sysmon fromMicrosoft Sysinternals
2. Use a tested config file like SwiftOnSecurity( more noise reduction) [download it from:](https://github.com/SwiftOnSecurity/sysmon-config)
3. Open command prompt as an administrator
4. install sysmon with this config : <pre><code> sysmon.exe -accepteula -i sysmonconfig-export.xml </code></pre>
