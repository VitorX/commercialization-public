---
title: IconID
description: IconID
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 619e7a64-483d-4b66-a9ed-9515bca22e25
ms.mktglfcycl: deploy
ms.sitesec: msdn
author: themar-msft
ms.author: themar
ms.date: 05/02/2017
ms.topic: article


---

# IconID


`IconID` specifies the full path to the resource DLL that contains the icon to use with [CustomPowerApplication3](microsoft-windows-stobject-custompowerapplication3.md).

This setting is optional.

To use a different IconID for each language, create a resource file, and refer to it using the format: "filename.dll,-referenceid". For information on creating localized text versions for this setting, see the topic [Using the MUI with Applications](http://go.microsoft.com/fwlink/?LinkId=140252).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>ID</em></p></td>
<td><p>Specifies the resource ID of the icon to use for <a href="microsoft-windows-stobject-custompowerapplication3.md" data-raw-source="[CustomPowerApplication3](microsoft-windows-stobject-custompowerapplication3.md)">CustomPowerApplication3</a>.</p>
<p><code>IconID</code> is represented as @<em>dllname,-resourceID</em>, where <em>dllname</em> must include a full path to the resource DLL. For example,</p>
<pre class="syntax" space="preserve"><code>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200.</code></pre>
<p><em>ID</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-stobject](microsoft-windows-stobject.md) | [CustomPowerApplication3](microsoft-windows-stobject-custompowerapplication3.md) | **IconID**

## Applies To


For a list of the supported Windows editions and architectures this component supports, see [Microsoft-Windows-stobject](microsoft-windows-stobject.md).

## XML Example


The following XML output shows `CustomPowerApplication3` Application.exe with `parameter -param`. `IconID` and `ItemName` are included in the Resource.dll file.

```
<CustomPowerApplication3>
   <Application>%ProgramFiles%\CustomPower\Application.exe</Application>
   <IconID>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200</IconID>
   <ItemName>%ProgramFiles%\Microsoft Shared\Resource.dll,-100</ItemName>
   <Parameters>-param</Parameters>
</CustomPowerApplication3>
```

## Related topics


[CustomPowerApplication3](microsoft-windows-stobject-custompowerapplication3.md)

 

 







