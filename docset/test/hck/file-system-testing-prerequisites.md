---
author: joshbax-msft
title: File System Testing Prerequisites
description: File System Testing Prerequisites
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2822edc9-02d3-47fb-8fa0-5904b18261c0
---

# File System Testing Prerequisites


This section describes the tasks that you must complete before you test an audio device by using the Windows Hardware Certification Kit (Windows HCK):

-   Review the hardware requirements.

-   Review the software requirements.

-   Configure the test computers.

## Hardware requirements


The following hardware is required for File System testing.

-   One test computer running a supported operating system. This computer must include the following:

    -   Windows keyboard

    -   Two-button pointing device (this is optional if the test computer is a laptop with a touch pad or other input capability).

    -   Color display monitor capable of at least 1024 by 768 resolution, 32-bits per pixel, 60 Hz

    -   Persistent storage (typically a hard drive) with a minimum of 20 GB available.

    -   A server running Windows 2008 R2 SP1 or later.

**Note**  
To certify your product for use on servers, the test computer must support four processors and a minimum of 1 GB of RAM. These system capabilities are required to test the Rebalance, D3 State, and Multiple Processor Group functionality of the device and driver. You do not need a computer that actually has more than 64 processors to test your device. Additionally, the server system(s) being used for device or driver testing must have Server Core installed prior to testing. For more information see [Windows Server Installation Options](http://go.microsoft.com/fwlink/p/?LinkID=251454).

If you use a pool of test computers to test your product, at least one computer in the pool must contain four processors and a minimum of 1 GB of RAM. Additionally, that computer must contain the product that you want to test. As long as the driver is the same on all the computers in the pool, the system creates a schedule to run against all test computers.

For tests that do not include a driver to test, such as hard disk drive tests, the Windows HCK scheduler constrains the tests that validate the device’s and driver’s Rebalance, D3 State and Multiple Processor Groups functionality to run on the default test computer. You must manually configure this computer to have multiple processor groups. The default computer is the first test computer in the list. Test personnel must make sure that the first test computer in the list meets the minimum hardware requirements.

 

**Note**  
Except for para-virtualization drivers (as defined by Logo Program Requirement Policy-0020), you may not use any form of virtualization when you test physical devices and their associated drivers for server certification or signature. All virtualization products do not support the underlying functionality that is required to pass the tests that relate to multiple processor groups, device power management, device PCI functionality, and other tests.

 

## Software requirements


The following software is required to run the File System tests:

-   The AV filter driver under test

    **Warning**  
    Make sure that you install the product on the test computer before you install the Windows HCK Client.

     

## <a href="" id="bkmk-configure"></a>Test system configuration


To configure the test system, follow these steps:

1.  Determine the letter assignment for each volume:

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td><p>NTFS</p></td>
    <td><p>g:</p></td>
    </tr>
    <tr class="even">
    <td><p>CNTFS</p></td>
    <td><p>i:</p></td>
    </tr>
    <tr class="odd">
    <td><p>Fat16</p></td>
    <td><p>k:</p></td>
    </tr>
    <tr class="even">
    <td><p>Fat32</p></td>
    <td><p>l:</p></td>
    </tr>
    <tr class="odd">
    <td><p>ExFat</p></td>
    <td><p>m:</p></td>
    </tr>
    <tr class="even">
    <td><p>UDF</p></td>
    <td><p>n:</p></td>
    </tr>
    </tbody>
    </table>

     

2.  On the client computer, make sure that the following volumes are present:

    -   NTFS 2gb

    -   ntfs compressed 2gb

    -   fat16 1gb

    -   Fat32 1gb

    -   Exfat 1gb

    -   UDF 2gb

3.  In the controller, modify the parameters on the jobs in the $\\WDK Tests\\Storage\\Filesystems section to point to test volumes, as follows:

    -   TxF2: Modify ntfs and cntfs to point to test volumes.

    -   ReparsePonts: Modify NTFS and CNTFS to point to test volumes

    -   Installable Filesystems filter test: Modify ntfs, cntfs, fat, fat32, exfat, and udf to point to test volumes.

    -   Antivirus Installable Filesystems filter test: Modify ntfs, cntfs, fat, fat32, exfat, and udf to point to test volumes.

    -   File IO test: Modify ntfs, cntfs, fat, fat32, exfat, and udf to point to test volumes.

    -   Mapped File IO test: Modify ntfs, cntfs, fat, fat32, exfat, and udf to point to test volumes.

    -   Object ID test: Modify ntfs, cntfs, fat, fat32, exfat, and udf to point to test volumes.

    -   Oplocks test: Modify ntfs, cntfs, fat, fat32, exfat, and udf to point to test volumes.

    -   Syscache test: Modify ntfs, cntfs, fat, fat32, exfat, and udf to point to test volumes.

4.  On the server, create a share that you name RDRTest.

5.  Modify the parameters in the $\\WDK Tests\\Leasing\\SMB\_OplockRDR test to point to the server name and share name.

Make sure that the test computer is in the ready state before you begin your testing. If a test requires parameters to be set before it is run, a dialog box will be displayed for that test. Review the specific test topic for more information.

Some Windows HCK tests require user intervention. When running tests for a submission, it is a best practice to run the automated tests in a block separately from manual tests. This prevents a manual test from interrupting completion of an automated test.

 

 





