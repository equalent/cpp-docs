---
title: "__vmx_vmwrite"
ms.date: "11/04/2016"
f1_keywords: ["__vmx_vmwrite"]
helpviewer_keywords: ["__vmx_vmwrite intrinsic", "VMWRITE instruction"]
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
---
# __vmx_vmwrite

**Microsoft Specific**

Writes the specified value to the specified field in the current virtual machine control structure (VMCS).

## Syntax

```
unsigned char __vmx_vmwrite(
   size_t Field,
   size_t FieldValue
);
```

#### Parameters

|Parameter|Description|
|---------------|-----------------|
|*Field*|[in] The VMCS field to write.|
|*FieldValue*|[in] The value to write to the VMCS field.|

## Return Value

0
The operation succeeded.

1
The operation failed with extended status available in the `VM-instruction error field` of the current VMCS.

2
The operation failed without status available.

## Remarks

The `__vmx_vmwrite` function is equivalent to the `VMWRITE` machine instruction. The value of the `Field` parameter is an encoded field index that is described in Intel documentation. For more information, search for the document, "Intel Virtualization Technical Specification for the IA-32 Intel Architecture," document number C97063-002, at the [Intel Corporation](https://software.intel.com/articles/intel-sdm) site, and then consult Appendix C of that document.

## Requirements

|Intrinsic|Architecture|
|---------------|------------------|
|`__vmx_vmwrite`|x64|

**Header file** \<intrin.h>

**END Microsoft Specific**

## See also

[Compiler Intrinsics](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmread](../intrinsics/vmx-vmread.md)