# Windows Authentication Monitoring – SPL Queries

## 1. Failed Login Attempts by User

```spl
index=soc_lab
| search event_id=4625
| stats count by user source_ip
| sort - count
```

## 2. Failed Login Attempts by Source IP

```spl
index=soc_lab
| search event_id=4625
| stats count as Failed_Attempts dc(user) as Targeted_Users values(user) as Users by source_ip
| sort - Failed_Attempts
```

## 3. Successful Login from the Identified Source IP

```spl
index=soc_lab
| search event_id=4624 source_ip="203.0.113.50"
| table timestamp source_ip user event_id action scenario
```

## 4. Account Lockout Events

```spl
index=soc_lab
| search event_id=4740
| table timestamp user source_ip event_id action
```

## 5. Potential Password Spraying Detection

```spl
index=soc_lab
| search event_id=4625
| stats count as Failed_Attempts dc(user) as Targeted_Users values(user) as Users by source_ip
| where Failed_Attempts >= 10 AND Targeted_Users >= 5
| sort - Failed_Attempts
```

## Note

The detection thresholds were selected for this simulated training dataset and should be adjusted according to the organization's environment and security requirements.
