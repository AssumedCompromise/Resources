<!-- DO-MD-DEVNOTES-START -->
<!-- DO-MD-DEVNOTES-END -->
<!-- DO-MD-LABHEADER-START -->
![][DO1sm]

| **Event ID References**              |
|:--------------------------------------|
 
 ![][Div1]
<!-- DO-MD-LABHEADER-END -->
<!-- DO-MD-LAB-START -->

## Direct References
* [Full Sysmon EventID List][evidsysmon]
* [Microsoft Threat Protection (WEB)][refmstp-web]
* [Microsoft Threat Protection (PDF)][refmstp-pdf]
* [Sysmon Modular](https://github.com/olafhartong/sysmon-modular)
* [LogRhythm Windows Event Log (WEB)](https://docs.logrhythm.com/docs/devices/ms-windows-event-log-sources)
* [LogRhythm Windows Event Log (PDF)](https://resources.logrhythm.com/Docs/LogRhythm-Device-Configuration-Guides-7.8.0-Syslog-Log-Sources-RevD.pdf)
* [TrustedSec SysmonCommunityGuide](https://github.com/DefensiveOrigins/SysmonCommunityGuide)

## Kerberoasting
* [4768][evid4768]: A Kerberos authentication ticket (TGT) was requested
* [4769][evid4769]: A Kerberos service ticket was requested 
* [4770][evid4770]: A Kerberos service ticket was renewed
* [4773][evid4773]: A Kerberos service ticket request failed
* [4771](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-10/security/threat-protection/auditing/event-4771): Kerberos pre-authentication failed
<blockquote>

### Kerberos Authentiation Detail
* **Service Name**: Name of service in Kerberos Realm to which the TGT request was sent, such as "krbtgt"
* **Service ID**: (SID)  Security Identifier, such as "S-1-5-21-DOMAIN_IDENTIFIER-502."  Will display resolved account name if possible.
* **NULL SID**: Result of 4768 failures
</blockquote>

## Authentication Manipulation
* [4624][evid4624]: An account was successfully logged on
* [4625][evid4625]: An account failed to log on
* [4627][evid4627]: Group membership information
* [4648][evid4648]: A logon was attempted using explicit credentials
* [4776][evid4776]: The computer attempted to validate the credentials for an account.
* [4634][evid4634]: An account was logged off
* [4647][evid4647]: User initiated logoff
* [4964][evid4964]: Special groups have been assigned to a new login
* [4672][evid4672]: Special privileges assigned to new logon
* [4717][evid4717]: System securit access was granted to an account (logon user right)
* [4673][evid4673]: A privileged service was called
* [4674][evid4764]: An operation was attempted on a privileged object
* [4610][evid4610]: An authentication package has been loaded by the Local Security Authority.

<blockquote>

### Authentication Logon Types
* 2: Interactive
* 3: Network
* 4: Batch
* 5: Service
* 7: Unlock 
* 8: NetworkCleartext (Typically IIS /w Basic Auth)
* 9: NewCredentials 
* 10: RemoteItneractive (RDP)
* 11: CachedInteractive (Logon with DCC)

### Authentication Impersonation Level
* Anonymous
* Default
* Delegate
* Identify
* Impersonate

</blockquote>

## Process Manipulation
* [4688][evid4688]: A new process has been created
* [4689][evid4689]: A process has exited
* [4696][evid4696]: A primary token was assigned to process
* [4690][evid4690]: An attempt was made to duplicate a handle to an object
* [4697][evid4697]: A service was installed on the system
* [Sysmon 25][evid25]: ProcessTampering (Process image change)


## PowerShell Operational/Audit/Transaction Logs
* 4100: PS Error (Operational)
* 4101: PS Activity (MS Windows PowerShell Event)
* 4102: PS Error (Operational)
* 4103: PS Event (MS Windows PowerShell Event)
* 4104: PS Script Execution
* 4105: PS Script Execution Start (Operational)
* 4106: PS Script Execution End (Operational)
* 40961: PS Console Starting
* 40962: PS Console Ready 
* 53249: PS Scheduled Job Start (Scheduled Task)
* 53250: PS Scheduled Job Completed (Scheduled Task)
* 24577: PS ISE Running Script

## Log Manipulation
* [1102][evid1102]: the audit log was cleared
* [1100][evid1100]: The event logging service has shut down

## Sysmon Events
* [1][evid1]: Process creation
* [2][evid2]: A process changed a file creation time
* [3][evid3]: Network Connection
* [4][evid4]: Sysmon service state changed
* [5][evid5]: Process terminated
* [6][evid6]: Driver loaded
* [7][evid7]: Image loaded
* [8][evid8]: CreateRemoteThread
* [9][evid9]: RawAccessRead
* [10][evid10]: ProcessAccess
* [11][evid11]: FileCreate
* [12][evid12]: RegistryEvent (Object create and delete)
* [13][evid13]: RegistryEvent (Value Set)
* [14][evid14]: RegistryEvent (Key and Value Rename)
* [15][evid15]: FileCreateStreamHash
* [16][evid16]: ServiceConfigurationChange
* [17][evid17]: PipeEvent (Pipe Created)
* [18][evid18]: PipeEvent (Pipe Connected)
* [19][evid19]: WmiEvent (WmiEventFilter activity detected)
* [20][evid20]: WmiEvent (WmiEventFilter activity detected)
* [21][evid21]: WmiEvent (WmiEventConsumerToFilter activity detected)
* [22][evid22]: DNSEvent (DNS query)
* [23][evid23]: FileDelete (File Delete archived)
* [24][evid24]: ClipboardChange (New content in the clipboard)
* [25][evid25]: ProcessTampering (Process image change)
* [26][evid26]: FileDeleteDetected (File Delete logged)
* [255][evid255]: Error

## Active Directory Object Manipulation
* [4662][evid4662]: An operation was performed by an object
* [4661][evid4661]: A handle to an object was requested
* [5136][evid5136]: A directory service object was modified
* [5137][evid5137]: A directory service object was created
* [5138][evid5138]: A directory service object was undeleted
* [5139][evid5139]: A directory service object was moved
* [5141][evid5141]: A directory service object was deleted
* [4670][evid4670]: Permissions on an object were changed
* [4715][evid4715]: The audit policy on an object was changed

## Active Directory (User) Account Management
* [4720][evid4720]: A user account was created
* [4722][evid4722]: A user account was enabled
* [4723][evid4723]: An attempt was made to change an account's password
* [4724][evid4724]: An attempt was made to reset an account's password
* [4725][evid4725]: A user account was disabled
* [4726][evid4726]: A user account was deleted
* [4738][evid4738]: A user account was changed
* [4740][evid4740]: A user account was locked out
* [4767][evid4767]: A user account was unlocked
* [4781][evid4781]: The name of an account was changed
* [4780][evid4780]: The ACL was set on accounts which are members of administrator groups (ADMIN=1)
* [4798][evid4798]: A user's local group membership was enumerated
* [4782][evid4782]: The password hash on an account was accessed
* [4670][evid4670]: Permissions on an object were changed
* [4715][evid4715]: The audit policy on an object was changed
* [4703][evid4703]: A user right was adjusted
* [4704][evid4704]: A user right was assigned
* [4705][evid4705]: A user right was removed

## Active Directory (Computer) Account Management
* [4741][evid4741]: A computer account was created
* [4742][evid4742]: A computer account was changed
* [4743][evid4743]: A computer account was deleted
* [4670][evid4670]: Permission on an object were changed

## Active Directory Security Group Management
* [4731][evid4731]: A security-enabled local group as created
* [4732][evid4732]: A member was added to a security-enabled local group
* [4733][evid4733]: A member was removed from a security-enabled local group
* [4735][evid4735]: A security-enabled local group was changed
* [4799][evid4799]: A security-enabled local group membership was enumerated
* [4670][evid4670]: Permission on an object were changed

## Active Directory Services - Misc
* [4706][evid4706]: A new trust was created to a domain
* [4707][evid4707]: A trust to a domain was removed
* [4716][evid4716]: Trusted domain information was modified
* [4739][evid4739]: Domain Policy was changed
* [6145][evid6145]: One or more errors occured while processign security policy in the group policy objects
* [ADCS](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn786423(v=ws.11)): Securing PKI Appendix

## Aduit File Share / System
* [5145][evid5145]: A network share object was checked to see whether client can be granted desired access
* [5140][evid5140]: A network share object was accessed
* [5142][evid5142]: A network share object was added
* [5143][evid5143]: A network share object was modified
* [5144][evid5144]: A network share object was deleted
* [5168][evid5168]: SPN check for SMB/SMB2 Failed
* [4670][evid4670]: Permission on an object were changed

## Windows Firewall
* [5157][evid5157]: The Windows Filtering Platform has blocked a connection
* [5158][evid5158]: The Windows Filtering Platform has permitted a bind to a local port
* [5159][evid5159]: The Windows Filtering Platform has blocked a bind to a local port
* [5152][evid5152]: The Windows Filtering Platform has blocked a packet
* [5447][evid5447]: A Windows Filtering Platform filter has been changed
* [5025][evid5025]: The Windows Firewall Service has been stopped

## Scheduled Tasks
* [4698][evid4698]: A scheduled task was created
* [4699][evid4699]: A scheduled task was deleted
* [4700][evid4700]: A scheduled task was enabled
* [4701][evid4701]: A scheduled task was disabled
* [4702][evid4702]: A scheduled task was updated
* [4717][evid4717]: System security access was granted to an account (logon user right)

## Registry Management
* [4663][evid4663]: An attempt was made to access an object
* [4656][evid4656]: A handle to an object was requested
* [4660][evid4660]: An object was deleted
* [4657][evid4657]: A registry value was modified
* [4670][evid4670]: Permission on an object were changed
* [Sysmon 12][evid12]: RegistryEvent (Object create and delete)
* [Sysmon 13][evid13]: RegistryEvent (Value Set)
* [Sysmon 14][evid14]: RegistryEvent (Key and Value Rename)

## Audit Policy
* [4719][evid4719]: System audit policy was changed
* [4715][evid4715]: The audit policy on an object was changed
* [4670][evid4670]: Permission on an object were changed
* [4817][evid4817]: Auditing settings on object were changed (Global)
* [4907][evid4907]: Auditing settings on object were changed (Object)
* [4908][evid4908]: Special Grouops Logon Table modified




<!-- DO-MD-LAB-END -->

<!-- DO-MD-FOOTER-START -->
![][Div1]

Copyright - All Rights Reserved, Defensive Origins LLC
<!-- DO-MD-FOOTER-END -->


<!-- DO-MD-SHORTCUTS-START -->
[1]: https://defensiveorigins.com/
[2]: https://wildwesthackinfest.com/training/
[APT]:https://github.com/DefensiveOrigins/AtomicPurpleTeam
[Cheat-Sheets]:9-Others/Cheatsheets/
[DefOrg]: https://defensiveorigins.com/
[Div1]: ../../Z-images/div/div1.png
[Div2]: ../../Z-images/div/div2.png
[DO]: https://www.defensiveorigins.com
[DO1]: ../../Z-images/logo/DO1.png
[DO1sm]: ../../Z-images/logo/DO1sm.png
[DOAboutUs]: https://defensiveorigins.com/about-us
[DOAZLab]: https://www.doazlab.com
[DOAZLab-Github]: https://github.com/DefensiveOrigins/DO-LAB
[DOImage]: ../../Z-images/do_darkbackground.jpg
[DOImage]:Z-images/do_darkbackground.jpg
[DORegister]: https://defensiveorigins.com/first-to-know/
[DOTraining]: https://training.defensiveorigins.com
[evid1]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/process-creation.md
[evid10]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/process-access.md
[evid11]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/file-create.md
[evid1100]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-1100
[evid1102]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-1102
[evid12]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/registry-actions.md
[evid13]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/registry-actions.md
[evid14]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/registry-actions.md
[evid15]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/file-stream-creation-hash.md
[evid16]: https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=90016
[evid17]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/named-pipes.md
[evid18]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/named-pipes.md
[evid19]: https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=90019
[evid2]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/file-create-time-change.md
[evid20]: https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=90020
[evid21]: https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=90021
[evid22]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/dns-query.md
[evid23]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/file_delete_detected.md
[evid24]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/clipboard-capture.md
[evid25]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/process-tampering.md
[evid255]: https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon
[evid26]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/file_delete_detected.md
[evid28]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/file-delete.md
[evid3]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/network-connections.md
[evid4]: https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=90004
[evid4610]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4610
[evid4624]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4624
[evid4625]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4625
[evid4627]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4627
[evid4634]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4634
[evid4647]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4647
[evid4648]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4648
[evid4656]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4656
[evid4657]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4657
[evid4660]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4660
[evid4661]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4661
[evid4662]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4662
[evid4663]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4663
[evid4670]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4670
[evid4672]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4672
[evid4673]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4673
[evid4688]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4688
[evid4689]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4689
[evid4690]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4690
[evid4696]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4696
[evid4697]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4697
[evid4698]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4698
[evid4699]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4699
[evid4700]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4700
[evid4701]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4701
[evid4702]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4702
[evid4703]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4703
[evid4704]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4704
[evid4705]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4705
[evid4706]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4706
[evid4707]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4707
[evid4715]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4715
[evid4716]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4716
[evid4717]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4717
[evid4719]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4719
[evid4720]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4720
[evid4722]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4722
[evid4723]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4723
[evid4724]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4724
[evid4725]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4725
[evid4726]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4726
[evid4731]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4731
[evid4732]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4732
[evid4733]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4733
[evid4735]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4735
[evid4736]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4736
[evid4738]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4738
[evid4739]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4739
[evid4740]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4740
[evid4741]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4741
[evid4742]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4742
[evid4743]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4743
[evid4764]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4764
[evid4765]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4765
[evid4767]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4767
[evid4768]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4768
[evid4769]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4769
[evid4770]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4770
[evid4773]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4773
[evid4776]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4776
[evid4780]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4780
[evid4781]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4781
[evid4782]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4782
[evid4798]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4798
[evid4799]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4799
[evid4817]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4817
[evid4907]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4907
[evid4908]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4908
[evid4964]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4964
[evid5]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/process-termination.md
[evid5025]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5025
[evid5136]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5136
[evid5137]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5137
[evid5138]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5138
[evid5139]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5139
[evid5140]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5140
[evid5141]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5141
[evid5142]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5142
[evid5143]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5143
[evid5144]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5144
[evid5145]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5145
[evid5152]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5152
[evid5157]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5157
[evid5158]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5158
[evid5159]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5159
[evid5168]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5168
[evid5447]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-5447
[evid6]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/driver-loading.md
[evid6145]: https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-6145
[evid7]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/image-loading.md
[evid8]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/create-remote-thread.md
[evid9]: https://github.com/DefensiveOrigins/SysmonCommunityGuide/blob/master/chapters/raw-access-read.md
[evidsysmon]: https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon
[H0004]: ../../../APT/9-Others/H0040-Instructors/
[H0010]: ../../../APT/9-Others/H0010-PreReq/
[ph_jd]: ../../Z-images/photo/jd1.png
[ph_ki]: ../../Z-images/photo/ki1.png
[refmstp-pdf]: https://docs.microsoft.com/en-us/windows/security/opbuildpdf/threat-protection/auditing/toc.pdf?branch=live
[refmstp-web]: https://docs.microsoft.com/en-us/windows/security/threat-protection/
[Survey]:https://forms.office.com/Pages/ResponsePage.aspx?id=ezi0P6h7Wky98F15YOOzAxFXFOo3MeNFpviudN0SuLhUMDNCT1NYWk5QWjlHUkMyMVhJVjFJTjhQMy4u
[WWHF]: https://wildwesthackinfest.com/
[addlogo]:../../Z-images/logo/add.png
[addlogosm]:../../Z-images/logo/addsm.png
<!-- DO-MD-SHORTCUTS-END -->
