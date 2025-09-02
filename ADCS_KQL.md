Mismatch SID Event
```
Event
| parse EventData with * 'AccountName">' TargetAccount "<" *
| parse EventData with * 'Subject">' Requester "<" *
| parse EventData with * 'Issuer">' Issuer "<" *
| where EventID == 39
| project TimeGenerated, EventID, TargetAccount, Requester,Issuer
```
Certificate Request Approved Event
```
SecurityEvent 
| where EventID == 4887
| project TimeGenerated, Requester, Attributes
```

Template Updated Events
```
SecurityEvent
| parse EventData with * 'TemplateInternalName">' TemplateName "<" *
| parse EventData with * 'NewSecurityDescriptor">' NewSecurityDescriptor "<" *
| parse EventData with * 'OldSecurityDescriptor">' OldSecurityDescriptor "<" *
| parse EventData with * 'NewTemplateContent">' NewTemplateContent "<" *
| parse EventData with * 'OldTemplateContent">' OldTemplateContent "<" *
| where EventID == 4899 or EventID  == 4900 
| project  EventID, TimeGenerated, TemplateName, NewSecurityDescriptor,OldSecurityDescriptor,NewTemplateContent,OldTemplateContent
```
