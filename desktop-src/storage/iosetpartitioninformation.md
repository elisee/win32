---
title: IoSetPartitionInformation routine
description: The IoSetPartitionInformation routine is obsolete and is provided only to support existing drivers.
ms.assetid: '3f1a6e3f-3bbc-4cc5-8efe-e3cf6ac3adf5'
keywords: ["IoSetPartitionInformation routine Storage Devices"]
topic_type:
- apiref
api_name:
- IoSetPartitionInformation
api_location:
- NtosKrnl.exe
api_type:
- DllExport
---

# IoSetPartitionInformation routine

The **IoSetPartitionInformation** routine is **obsolete** and is provided only to support existing drivers. New drivers must use [**IoSetPartitionInformationEx**](iosetpartitioninformationex.md).

**IoSetPartitionInformation** sets the partition type and number in a partition table entry for the disk represented by *DeviceObject*.

## Syntax


```C++
NTSTATUS FASTCALL IoSetPartitionInformation(
  _In_�PDEVICE_OBJECT DeviceObject,
  _In_�ULONG ���������SectorSize,
  _In_�ULONG ���������PartitionNumber,
  _In_�ULONG ���������PartitionType
);
```



## Parameters

<dl> <dt>

*DeviceObject* \[in\]
</dt> <dd>

Pointer to the device object representing the device on which the partition type is to be set.

</dd> <dt>

*SectorSize* \[in\]
</dt> <dd>

Specifies the size, in bytes, of sectors on the disk.

</dd> <dt>

*PartitionNumber* \[in\]
</dt> <dd>

Specifies the partition number on the device whose partition type is to be set.

</dd> <dt>

*PartitionType* \[in\]
</dt> <dd>

Specifies the type for the partition. For a list of some of the key partition types see [**PARTITION\_INFORMATION**](partition-information.md).

</dd> </dl>

## Return value

If **IoSetPartitionInformation** returns STATUS\_SUCCESS, the disk driver updates its notion of the partition type for this partition in its device extension.

## Remarks

**IoSetPartitionInformation** must only be used by disk drivers. Other drivers should use the [**IOCTL\_DISK\_SET\_PARTITION\_INFO**](ioctl-disk-set-partition-info.md) disk I/O request instead.

This routine is called when a disk device driver is asked to set the partition type in a partition table entry by an IRP\_MJ\_DEVICE\_CONTROL request. This request is generally issued by the format utility, which performs I/O control functions on the partition. The driver passes a pointer to the device object representing the physical disk and the number of the partition associated with the device object that the format utility has open. Since the HAL routines that underlie **IoSetPartitionInformation** were developed before support of dynamic partitioning was implemented, they do not distinguish between the *partition ordinal* (that is the order of a partition on a disk) and the *partition number* (the partition number assigned to a partition in order to identify it to the system). Drivers must call **IoSetPartitionInformation** using the *ordinal* number of the partition and not the actual partition number.

This routine is synchronous and must be called by the disk driver's Dispatch routine or by a driver thread. Thus, all user and file system threads must be prepared to enter a wait state when issuing the device control request to set the partition type for the device.

This routine operates under the assumption that the partition number passed in by the disk driver actually exists.

This routine must be called at IRQL = PASSIVE\_LEVEL because it uses a kernel event object to synchronize I/O completion on the device. The event cannot be set to the Signaled state without queuing and executing the I/O system's special kernel APC routine for I/O completion.

## Requirements



|                                 |                                                                                                                                         |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| Target platform<br/>      | <dl> <dt>[Universal](http://go.microsoft.com/fwlink/p/?linkid=531356)</dt> </dl> |
| Header<br/>               | <dl> <dt>Ntddk.h (include Ntddk.h)</dt> </dl>                                    |
| Library<br/>              | <dl> <dt>NtosKrnl.lib</dt> </dl>                                                 |
| DLL<br/>                  | <dl> <dt>NtosKrnl.exe</dt> </dl>                                                 |
| IRQL<br/>                 | PASSIVE\_LEVEL (See Remarks section)<br/>                                                                                         |
| DDI compliance rules<br/> | [**HwStorPortProhibitedDDIs**](https://msdn.microsoft.com/library/windows/hardware/hh454220)                                                               |



## See also

<dl> <dt>

[**IoReadPartitionTable**](ioreadpartitiontable.md)
</dt> <dt>

[**IoWritePartitionTable**](iowritepartitiontable.md)
</dt> <dt>

[**IoSetPartitionInformationEx**](iosetpartitioninformationex.md)
</dt> </dl>

�

�

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bstorage\storage%5D:%20IoSetPartitionInformation%20routine%20%20RELEASE:%20%283/29/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





