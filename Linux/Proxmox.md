---
title: Ceph
description: 
published: true
date: 2025-04-10T02:57:18.545Z
tags: 
editor: markdown
dateCreated: 2025-04-10T02:57:18.545Z
---

# Documentation
https://pve.proxmox.com/pve-docs/chapter-pveceph.html
https://docs.ceph.com/en/latest/

# Reference
## List placement groups by pool
```
ceph pg ls-by-pool <pool>
```

## CRUSH MSR (multi-step retry) rule
https://docs.ceph.com/en/latest/dev/crush-msr/
```
rule msr_rule {
    id 2
    type msr_firstn
    step take default
    step choosemsr 3 type host
    step choosemsr 2 type osd
    step emit
}
```


## Manually edit CRUSH map
https://docs.ceph.com/en/latest/rados/operations/crush-map-edits/

### Dump
```
ceph osd getcrushmap -o crush.map
```

### Decompile
```
crushtool -d crush.map -o crush.dmap
```

### Edit
```
nano crush.dmap
```

### Compile
```
crushtool -c crush.dmap -o crush.map
```

### Import
```
ceph osd setcrushmap -i crush.map
```