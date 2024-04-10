```
parted /dev/sda resizepart $(blkid|grep /dev/sda|sort|tail -n 1|cut -c 9) 100%
pvresize /dev/sda$(blkid|grep /dev/sda|sort|tail -n 1|cut -c 9)

```
chạy kiểm tra vgs và lvs
```
lvextend -l +100%FREE /dev/vg0/lv-0
resize2fs /dev/vg0/lv-0
```
