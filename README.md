# Vagrantfile, который сразу собирает систему с подключенным рейдом + GPT раздел, пять партиций
В Vagrantfile provision содержится ссылка на приложенный скрипт mdadm.sh, в котором создаётся raid5 + GPT раздел, пять партиций.
В итоге на развёрнутой vm по команде ```mdadm -D /dev/md0``` будет получен следующий результат

```
[root@otushomework vagrant]# mdadm -D /dev/md0
/dev/md0:
           Version : 1.2
     Creation Time : Tue Nov 19 18:01:26 2019
        Raid Level : raid5
        Array Size : 1013760 (990.00 MiB 1038.09 MB)
     Used Dev Size : 202752 (198.00 MiB 207.62 MB)
      Raid Devices : 6
     Total Devices : 6
       Persistence : Superblock is persistent

       Update Time : Tue Nov 19 18:02:38 2019
             State : clean 
    Active Devices : 6
   Working Devices : 6
    Failed Devices : 0
     Spare Devices : 0

            Layout : left-symmetric
        Chunk Size : 512K

Consistency Policy : resync

              Name : otushomework:0  (local to host otushomework)
              UUID : 80937933:52f6ae01:7c1567b1:c91710f8
            Events : 106

    Number   Major   Minor   RaidDevice State
       0       8       16        0      active sync   /dev/sdb
       1       8       32        1      active sync   /dev/sdc
       2       8       48        2      active sync   /dev/sdd
       3       8       64        3      active sync   /dev/sde
       4       8       80        4      active sync   /dev/sdf
       6       8       96        5      active sync   /dev/sdg
```
