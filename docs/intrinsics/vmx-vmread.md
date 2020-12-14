---
description: '詳細については、次を参照してください: __vmx_vmread'
title: __vmx_vmread
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmread
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
ms.openlocfilehash: 39ea9c0566d3f9c9d3fc6d980861fb3580293895
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333509"
---
# <a name="__vmx_vmread"></a>__vmx_vmread

**Microsoft 固有の仕様**

現在の仮想マシン制御構造 (VMCS) から指定されたフィールドを読み取り、指定された場所に配置します。

## <a name="syntax"></a>構文

```C
unsigned char __vmx_vmread(
   size_t Field,
   size_t *FieldValue
);
```

### <a name="parameters"></a>パラメーター

*分野*\
から読み取る VMCS フィールド。

*FieldValue*\
からパラメーターで指定した VMCS フィールドから読み取った値を格納する場所へのポインター `Field` 。

## <a name="return-value"></a>戻り値

|値|意味|
|-----------|-------------|
|0|操作が成功しました。|
|1|現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。|
|2|有効な状態がないため操作は失敗しました。|

## <a name="remarks"></a>解説

`__vmx_vmread` 関数は `VMREAD` マシン語命令と同じです。 パラメーターの値 `Field` は、Intel のドキュメントで説明されているエンコードされたフィールドインデックスです。 詳細については、 [Intel Corporation](https://software.intel.com/articles/intel-sdm) のサイトの「IA-32 intel アーキテクチャの Intel Virtualization Technical Specification」を参照してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__vmx_vmread`|X64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)
