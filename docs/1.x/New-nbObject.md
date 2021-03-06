---
external help file: powerbox-help.xml
Module Name: powerbox
online version:
schema: 2.0.0
---

# New-nbObject

## SYNOPSIS
Sets properties on a object in Netbox

## SYNTAX

```
New-nbObject [-Resource] <String> [[-CustomProperties] <String[]>] [[-Lookup] <Hashtable>]
 [[-Properties] <Object>] [<CommonParameters>]
```

## DESCRIPTION
This should handle mapping a simple hashtable of values and looking up any references.

## EXAMPLES

### EXAMPLE 1
```
$lookup = @{
```

device_type='dcim/device-types'
    device_role='dcim/device-roles'
    site='organization/sites'
    status='dcim/_choices'
}
$device = @{
    name = 'example'
    serial = 'aka123457'
    device_type = 'dl380-g9'
    device_role = 'oracle'
    site = 'chicago'
    status = 'active'
}
Set-nbObject -resource dcim/devices -id 22 -lookup $lookup @device

### EXAMPLE 2
```
Set-nbObject -resource dcim/devices -id 22 -name example2 -serial madeup -device_type dl380-gen8 -site chicago -lookup device_type,site
```

## PARAMETERS

### -CustomProperties
List of custom properties

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lookup
List of properties to lookup

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Properties
you can specify properties as arguments to this command

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Resource
object/resource type```yaml
Type: String
Parameter Sets: (All)
Aliases: type, object

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
