---
description: '詳細については、次を参照してください: __vmx_vmwrite'
title: __vmx_vmwrite
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmwrite
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
ms.openlocfilehash: d8902d51b05fa96faf22cbb6d80400e1f67c5f3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257304"
---
# <a name="__vmx_vmwrite"></a>__vmx_vmwrite

**Microsoft 固有の仕様**

現在の仮想マシン制御構造 (VMCS) 内の指定されたフィールドに、指定された値を書き込みます。

## <a name="syntax"></a>構文

```C
unsigned char __vmx_vmwrite(
   size_t Field,
   size_t FieldValue
);
```

### <a name="parameters"></a>パラメーター

*分野*\
から書き込む VMCS フィールド。

*FieldValue*\
からVMCS フィールドに書き込む値。

## <a name="return-value"></a>戻り値

0
操作が成功しました。

1
現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。

3
有効な状態がないため操作は失敗しました。

## <a name="remarks"></a>解説

`__vmx_vmwrite` 関数は `VMWRITE` マシン語命令と同じです。 パラメーターの値 `Field` は、Intel のドキュメントで説明されているエンコードされたフィールドインデックスです。 詳細については、 [Intel Corporation](https://software.intel.com/articles/intel-sdm) のサイトの「IA-32 intel アーキテクチャの Intel Virtualization Technical Specification」を参照してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__vmx_vmwrite`|X64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmread](../intrinsics/vmx-vmread.md)
