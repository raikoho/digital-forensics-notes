
|   |   |
|---|---|
|Windows.cmdline|Lists process command line arguments|
|windows.drivermodule|Determines if any loaded drivers were hidden by a rootkit|
|Windows.filescan|Scans for file objects present in a particular Windows memory image|
|Windows.getsids|Print the SIDs owning each process|
|Windows.handles|Lists process open handles|
|Windows.info|Show OS & kernel details of the memory sample being analyzed|
|Windows.netscan|Scans for network objects present in a particular Windows memory image|
|Widnows.netstat|Traverses network tracking structures present in a particular Windows memory image.|
|Windows.mftscan|Scans for Alternate Data Stream|
|Windows.pslist|Lists the processes present in a particular Windows memory image|
|Windows.pstree|List processes in a tree based on their parent process ID|

**Example:**

```
user@machine$ vol -f memdump.mem windows.info
```

Observing any potential network activity
```
vol -f memdump.mem windows.netstat
```
![[Pasted image 20250118185055.png]]