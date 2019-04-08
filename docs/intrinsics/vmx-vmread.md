---
title: __vmx_vmread
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmread
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
ms.openlocfilehash: 5c7b72ba3bf1bd60324704b774bcedaf5612240f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028387"
---
# <a name="vmxvmread"></a>__vmx_vmread

**Microsoft 固有の仕様**

現在の仮想マシン制御構造 (VMCS) から指定したフィールドを読み取り、指定した場所に配置します。

## <a name="syntax"></a>構文

```
unsigned char __vmx_vmread(
   size_t Field,
   size_t *FieldValue
);
```

#### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*フィールド*|[in]読み取る VMCS フィールド。|
|*FieldValue*|[in]によって指定された VMCS フィールドから値を格納する場所へのポインターを読み取る、`Field`パラメーター。|

## <a name="return-value"></a>戻り値

|[値]|説明|
|-----------|-------------|
|0|操作が成功しました。|
|1|現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。|
|2|有効な状態がないため操作は失敗しました。|

## <a name="remarks"></a>Remarks

`__vmx_vmread` 関数は `VMREAD` マシン語命令と同じです。 値、`Field`パラメーターは、Intel のドキュメントで説明されているエンコードされたフィールドのインデックス。 詳細については、検索、ドキュメント、「Intel 仮想化技術仕様 ia-32 Intel アーキテクチャ向け、」で番号 C97063-002、文書化、 [Intel Corporation](https://software.intel.com/articles/intel-sdm)サイト、し、そのドキュメントの「付録 C を参照してください.

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__vmx_vmread`|X64|

**ヘッダー ファイル** \<intrin.h >

**END Microsoft 固有の仕様**

## <a name="see-also"></a>関連項目

[コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)