---
layout: post
title:  "Migrar aliases a zimbra"
date:   2022-04-18 12:19:23 -0300
categories: zimbra linux
---
Si quieren migrar el archivo aliases a zimbra, usen este simple conversor:

```shell
for LL in $(cut -d: -f1 listas.txt); do
    for UU in $(grep $LL listas.txt |cut -d: -f2|\
        sed 's/,/ /g'); do
        echo $UU '-->' $LL
        zmprov adlm $LL@domain.com $UU@domain.com
    done
done
```
