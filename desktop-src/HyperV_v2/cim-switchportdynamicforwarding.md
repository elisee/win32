---
Description: 'Represents an association in which an entry of a forwarding database applies to a switch port.'
ms.assetid: 'e63ac61d-ed0c-49e9-b056-4fcb6d1d5455'
title: 'CIM\_SwitchPortDynamicForwarding class'
---

# CIM\_SwitchPortDynamicForwarding class

Represents an association in which an entry of a forwarding database applies to a switch port.

## Syntax

``` syntax
[Association, Abstract, Version("2.7.0"), UMLPackagePath("CIM::Network::SwitchingBridging"), AMENDMENT]
class CIM_SwitchPortDynamicForwarding : CIM_Dependency
{
  CIM_SwitchPort������������ REF Antecedent;
  CIM_DynamicForwardingEntry REF Dependent;
};
```

## Members

The **CIM\_SwitchPortDynamicForwarding** class has these types of members:

-   [Properties](#properties)

### Properties

The **CIM\_SwitchPortDynamicForwarding** class has these properties.

<dl> <dt>

**Antecedent**
</dt> <dd> <dl> <dt>

Data type: **CIM\_SwitchPort**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**Override**](https://msdn.microsoft.com/library/aa393650) ("Antecedent"), [**Min**](https://msdn.microsoft.com/library/aa393650) (1)
</dt> </dl>

A [**CIM\_SwitchPort**](cim-switchport.md) reference to the switch port.

</dd> <dt>

**Dependent**
</dt> <dd> <dl> <dt>

Data type: **CIM\_DynamicForwardingEntry**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**Override**](https://msdn.microsoft.com/library/aa393650) ("Dependent")
</dt> </dl>

A [**CIM\_DynamicForwardingEntry**](cim-dynamicforwardingentry.md) reference to the entry of the forwarding database.

</dd> </dl>

## Requirements



|                                     |                                                                                                         |
|-------------------------------------|---------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�8<br/>                                                                                    |
| Minimum supported server<br/> | Windows Server�2012<br/>                                                                          |
| Namespace<br/>                | Root\\virtualization\\v2<br/>                                                                     |
| MOF<br/>                      | <dl> <dt>WindowsVirtualization.V2.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Vmms.exe</dt> </dl>                     |



## See also

<dl> <dt>

[**CIM\_Dependency**](cim-dependency.md)
</dt> </dl>

�

�



