# Check Disk Status

# fdisk - Partition table manipulator for Linux

Manipulate disk partition table

    # fdisk -l
    # fdisk -l /dev/sda
    # fdisk -lu /dev/sda

# df - report file system disk space usage

    # df -h

# iostat/sysstat - report cpu, io, NFS statistics.

iostat - Report Central Processing Unit(CPU) statistics and input/output statistics for devices, partitions and network filesystems(NFS).

Install

    # yum -y install sysstat

Check I/O status

    # iostat -d -x -k 1 5
    Device:         rrqm/s   wrqm/s     r/s     w/s    rkB/s    wkB/s avgrq-sz avgqu-sz   await  svctm  %util
    sda               0.02    14.17    0.05   33.57     0.75   190.95    11.40     0.29    8.76   5.51  18.52
    dm-0              0.00     0.00    0.07   47.94     0.73   190.95     7.98     1.26   26.15   3.86  18.53
    dm-1              0.00     0.00    0.00    0.00     0.00     0.00     8.00     0.00    2.44   1.67   0.00
    dm-2              0.00     0.00    0.00    0.00     0.00     0.00     7.87     0.00   18.83   8.78   0.00

|Parameter|Description|Note|
+---------+-----------+----+
|rrqm/s|The number of read requests merged per second that were queued to the device.||
|wrqm/s|The number of write requests merged per second that were queued to the device.||
|r/s|The number of read requests that were issued to the device per second.||
|w/s|The number of write requests that were issued to the device per second.||
|rKB/s|The number of kilobytes read from the device per second. Half of rsect/s(because each sector is 512 byte).|
|wKB/s|The number of kilobytes written to the device per second.||
|avgrq-sz|The average size (in sectors) of the requests that were issued to the device.|delta(rsect+wsect)/delta(rio+wio).|
|avgqu-sz|The average queue length of the requests that were issued to the device.|delta(avgq)/s/1000.|
|await|The  average  time  (in milliseconds) for I/O requests issued to the device to be served.|delta(ruse+wuse)/delta(rio+wio). Depends on service time(scvtm), queue length, and requst method. It had better less than 5ms.|
|svctm|The average service time (in milliseconds) for I/O requests that were issued to the device. delta(use)/delta(rio+wio).|Warning! Do not trust this field any more. Will be removed.|
|%util|Percentage  of  CPU time during which I/O requests were issued to the device (bandwidth utilization for the device).|Device saturation occurs when this value is close to 100%.|

# du - estimate file space usage

    # du -sh /opt
    # du -cks * | sort -rn | head -n 10

# dd - convert and copy a file



