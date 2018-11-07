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
  - The Universal Task supports both Universal Agent for Linux/Unix and Windows however it has been currently only tested against a Linux       Agent
  - You can select different log-levels e.g. Info and debug
  - All Passwords are encrypted using Controller Credentials
  - Currently only the InsecureClient (the default) is implemented the TokenClient can be implemented on request
  - Currently only direct file matches are implemented as this is the standard functionality supported by the hdfs python module. A scan       for files using wildcards or even regular expression can be implemented on request. 

# 4	Installation
# 4.1	Software Requirements for Linux Agent

**Universal Template name: UT-HDFS-FILE-MONITOR-LINUX**

Related UAC XML Files for template and task: [2]

Requirements: 
  - Python 3.6
  - For Python the following modules are required: 
      - os, for linux command execution
      - datetime and time to compare file timestamps
  - hdfs to perform the hdfs file operations
  - logging, for python loglevel support

Note: Only the module hdfs needs to be added via python installer 
 
 **pip install hdfs**
 
  - Universal Controller V6.4.7.0 or higher
  - Universal Agent V6.5.0.0 or higher installed on a Linux Server


# 4.2	Installation Steps
The following describes the installation steps:

**1.	Check the current Python Version**

python -V  (Note: Captial “V”)

If your Version is Python 3.6 or later all is fine. If a no python or a lower Version has been installed upgrade your python Version or 
install the Universal Agent with the Python binding option (--python yes). This option will install python 3.6. along with your 
universal agent.

e.g.
sudo sh ./unvinst --network_provider oms --oms_servers 7878@192.168.88.12 --oms_port 7878 --oms_autostart no --ac_netname OPSAUTOCONF --
opscli yes --python yes

**2.	Add the required python modules**

In a command shell run as sudo or root:
  - For Python the following modules are required: 
      - pip install hdfs
      or in case of universal Agent with python binding: 
      /opt/universal/python3.6/bin/python3 -m pip install hdfs
Only run these if not available already:
  - pip install datetime
  - pip install logging
  - pip install os
  
Note: 

It is assumed that the modules logging, sys, datetime, os are already available. If not install them via pip. Only the module hdfs is
usually not part of your installation.

https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads#bookmark-vs2013 

**3.	Import the Universal Task including the Universal Template to your Controller**
Go to “All Tasks” and load via the Import functionality the Universal Task configuration into the Controller. 

Image 1:

Image 2:

# 5	Universal Task Configuration

**1.	Activate: Resolvable Credentials in Universal Automation Center properties:**

Image 3 :


**2.	Fill Out the Universal Task for hdfs file monitoring:**

Image 4 :

Credential for Universal Task:

Image 5:

**Description:**

Image 6:

# 6	Test Cases

The following basic test cases has been performed

Image 7:

Image 8:

Image 9:

# 7	Document References

This document references the following documents:

Image 10:







