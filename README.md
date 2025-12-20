# check_linux_security_posture
nagios check for showing Linux security posture

# Requirements
perl, SSH key pair auth

# Configuration
Add a section similar to the following to the services.cfg file on the nagios server.
```
define service{
        use                             generic-service
        host_name                       linux01.example.com
        service_description             linux security posture
        check_command                   check_by_ssh!"/usr/local/nagios/libexec/check_linux_security_posture"
        }
```

# Output
You will see output similar to the following:
```
 linux_version:RHEL8.9 days_since_patch:70 date_of_last_patch:2024-03-07 selinux:Permissive firewall:active fail2ban:active auditd:active fapolicyd:no aide:1 arcticwolf:active sentinelone:no crowdstrike:active clamav:no msdefender:no | days_since_patch=70;;;;
```
