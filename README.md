# ut-hdfs-file-monitor-linux
This Universal Task provides a file monitor and optionally trigger, which monitors a file on the Hadoop HDFS file system. If the file is
found the file monitor goes to success or can optionally launch automatically a Universal Controller Task. It also possible to run the Task
monitor in auto restart mode, which means it re-starts itself automatically after it found a file.

# Abstract:
This Universal Task provides a file monitor and optionally trigger, which monitors a file on the Hadoop hdfs file system. If the file is
found the file monitor goes to success or can optionally launch automatically a Universal Controller Task. It also possible to run the Task 
monitor in auto restart mode, which means it re-starts itself automatically after it found a file. 

# 1	Disclaimer
No support and no warranty are provided by Stonebranch GmbH for this document and the related Universal Task. The use of this document and 
the related Universal Task is on your own risk.
Before using this task in a production system, please perform extensive testing.
Stonebranch GmbH assumes no liability for damage caused by the performance of the Universal Tasks

# 2	Scope 
This document provides a documentation how to install and use the Universal Tasks for hdfs file monitoring and triggering.  

# 3	Introduction
This Universal Task provides a file monitor and optionally trigger, which monitors a file on the Hadoop hdfs file system. If the file is 
found the file monitor goes to success or can optionally launch automatically a Universal Controller Task. It also possible to run the Task 
monitor in auto restart mode, which means it re-starts itself automatically after it found a file.

Some details about the universal task to monitor a value in a database column

  - The Universal Task uses the Python hdfs module, which calls the Hadoop WebHDFS REST API
The Universal Task supports both Universal Agent for Linux/Unix and Windows however it has been currently only tested against a Linux Agent
You can select different log-levels e.g. Info and debug
All Passwords are encrypted using Controller Credentials
Currently only the InsecureClient (the default) is implemented the TokenClient can be implemented on request
Currently only direct file matches are implemented as this is the standard functionality supported by the hdfs python module. A scan for 
files using wildcards or even regular expression can be implemented on request. 

