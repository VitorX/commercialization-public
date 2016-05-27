---
author: joshbax-msft
title: Win7.MBN.GSM.TestPin
description: Win7.MBN.GSM.TestPin
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a2609b3f-41b8-4e8d-b8bf-22c1d62014b8
---

# Win7.MBN.GSM.TestPin


The test will enable and disable PIN1 if supported. If PUK1 is supported the test will enter an incorrect pin until the PUK1 is activated

## Test details


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Associated requirements</strong></p></td>
<td><p>Device.Network.MobileBroadband.GSM.ComplyWithBaseReq</p>
<p>[See the device hardware requirements.](http://go.microsoft.com/fwlink/p/?linkid=254483)</p></td>
</tr>
<tr class="even">
<td><p><strong>Platforms</strong></p></td>
<td><p>Windows 7 (x64) Windows 7 (x86)</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected run time</strong></p></td>
<td><p>~10 minutes</p></td>
</tr>
<tr class="even">
<td><p><strong>Categories</strong></p></td>
<td><p>Basic Certification</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type</strong></p></td>
<td><p>Automated</p></td>
</tr>
</tbody>
</table>

 

## Running the test


Before you run the test, complete the test setup as described in the test requirements: [Mobile Broadband Testing Prerequisites](mobile-broadband-testing-prerequisites.md).

## Troubleshooting


For troubleshooting information, see [Troubleshooting Device.Network Testing](troubleshooting-devicenetwork-testing.md).

## More information


### Parameters

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PIN1</p></td>
<td><p>Specifies the PIN1 to use on the device.</p></td>
</tr>
<tr class="even">
<td><p>PUK1</p></td>
<td><p>Specifies the PUK1 to use on the device.</p></td>
</tr>
</tbody>
</table>

 

 

 





