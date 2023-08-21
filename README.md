# Verify your AD Healt

Run command in CMD context
## Replication Status
```
repadmin /showrepl
repadmin /replsummary
pause
```

## FSMO Role
```
netdom query fsmo
pause
```

## Force Replication
```
repadmin /syncall /AdePq
```
