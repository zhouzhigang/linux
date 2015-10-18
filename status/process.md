# Process

## ps - report a snapshot of the current processes

|Argument|Description|
+--------+-----------+
|a|Lift the BSD-style "only yourself" restriction.|
|-A, -e|Select all processes|
|-a|Select all processes except both session leaders.|
|-f|Do full-format listing.|
|u|Display user-oriented format.|

To see every process on the system using standard syntax:

    $ ps -ef | grep "mingett[y]"
    $ ps -ef | grep "logi[n]"

To see every process on the system using BSD syntax:

    $ pas ax
    $ ps axu

To print a process tree

    $ ps -ejH
    $ ps axjf

To get info about threads

    $ ps -eLf
    $ ps axms

# top

# netstat - network status and port

    $ netstat -tulpn

# service - run a System V init script

