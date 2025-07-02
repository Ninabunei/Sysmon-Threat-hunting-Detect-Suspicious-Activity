# Sysmon-Threat-hunting-Detect-Suspicious-Activity
I'll be using sysmon in a VM to detect suspicious activity
## GOAL
 To use Sysmon on a windows VM to detect suspecious activity like process injection, network connections or exection of unsigned binaries 
## STEP ONE 
1. Download sysmon fromMicrosoft Sysinternals
2. Use a tested config file like SwiftOnSecurity( more noise reduction) [download it from:](https://github.com/SwiftOnSecurity/sysmon-config)
3. Open command prompt as an administrator
4. install sysmon with this config : <pre><code> sysmon.exe -accepteula -i sysmonconfig-export.xml </code></pre>
## SIMULATE SUSPECIOUS ACTIVITY 
 1. FIRST SIMULATION: RUN A COMMAND FROM COMMAND PROMPT 
    a) Open command prompt as admin
    b) Run this command: <pre><code> ping 127.0.0.1 -n 3 </code></pre>
    c) Go to event viewer - applications and service logs - microsoft - windows- sysmon- operational and look out for event ID 1
    you should see the ping event id 1 with a parent image of cmd.exe
 2. SIMULATION 2: NETWORK CONNECTION FROM POWERSHELL
    a) Open PowerShell as an administrator
    b) Run : <pre><code> Invoke-WebRequest -Uri http://testphp.vulnweb.com </code></pre>
    This tries to connect to a test website used for learning security.
    N/B: You are not downloading malware, just simulating network traffic
    c) In event viewer, look for event ID 3 it will indicate
       image: powershell.exe
       DestinationIP: IP of the website
       DestinationPort: 80
       Protocol: TCP
  
    
