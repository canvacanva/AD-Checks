# Check Active Directory health

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

## Check Status
```
For /f %i IN ('dsquery server -o rdn') do @echo %i && @wmic /node:"%i" /namespace:\\root\microsoftdfs path dfsrreplicatedfolderinfo WHERE replicatedfoldername='SYSVOL share' get replicationgroupname,replicatedfoldername,state
```
```
The state values can be any of:
0 = Uninitialized
1 = Initialized
2 = Initial Sync
3 = Auto Recovery
4 = Normal
5 = In Error
```
