## Mes commandes utiles - spécial AIX  

Udemy cours AIX 7.2
https://www.udemy.com/share/103fkQ3@OLOXuWNI1LdDQdd9VDCbTJUEwHWSb5zJiasDhthNiEfOVfqU6VWqpVK1Of8KEXfd4A==/

Check os:
```
oslevel -s
```


Monitor os
```
topas
```


List all services
```
lssrc -a
```

Start a service 
```
startsrc -s <service_name>
```

Status of a service
```
lssrc -a | grep <service_name>
```

Stop service
```
stopsrc -s <service_name>
```

Shutdown AIX
```
shutdown -Fr
```

### SMIT

System Management Interface Tool - interactive tool bundled with AIX
Virtually any system administration-related task can be completed using a SMIT screen 
The screen are logically grouped in a hierarchal manner for easy navigation
Fast paths associated with every function can be used to go directly to the relevant screen

To create a user 
```
smit mkuser
smitty mkuser
```

To create a volume group
```
smit vg
smitty vg
```

To create a logical volume
```
smit lv
smitty lv
```

To create a filesystem
```
smit fs
smitty fs
```

### Logical Volume Management

Check physical disk
```
lspv
```

Configures devices and optionally installs device software into the system
```
cfgmgr
```

List volume group
```
lsvg -l <vg>
```

Create volume group
```
mkvg -y <volume_group> -s <size_mb> <disk>
```

Create logical volume 
The format : https://www.ibm.com/docs/en/aix/7.2?topic=performance-file-system-types
```
mklv -y <logical_volume> -t <format> <volume_group> 2
```

Format LV
```
crfs -v <format> -d <logical_volume> -m <mounting_point> -A yes -p rw
```

Remove LV
```
unmount <mounting_point>
rmfs <mounting_point>   
```

Remove VG
```
reducevg -d -f <volume_group> <physical_disk>
```

Remove PV
```
rmdev -Rdl <disk_name>
```
