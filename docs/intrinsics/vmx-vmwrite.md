---
title: __vmx_vmwrite
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmwrite
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
ms.openlocfilehash: e52b1f181f00ce013a111d1a5a62abeff544e20a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037511"
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite

**Microsoft 固有の仕様**

現在の仮想マシン制御構造 (VMCS) で指定されたフィールドに指定した値を書き込みます。

## <a name="syntax"></a>構文

```
unsigned char __vmx_vmwrite(
   size_t Field,
   size_t FieldValue
);
```

#### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*フィールド*|[in]書き込み先の VMCS フィールド。|
|*FieldValue*|[in]VMCS フィールドに書き込む値。|

## <a name="return-value"></a>戻り値

0 は、操作が成功しました。

1 使用可能な拡張状態、操作に失敗しました、`VM-instruction error field`現在 VMCS の。

2 状態を利用せず、、操作が失敗しました。

## <a name="remarks"></a>Remarks

`__vmx_vmwrite` 関数は `VMWRITE` マシン語命令と同じです。 値、`Field`パラメーターは、Intel のドキュメントで説明されているエンコードされたフィールドのインデックス。 詳細については、検索、ドキュメント、「Intel 仮想化技術仕様 ia-32 Intel アーキテクチャ向け、」で番号 C97063-002、文書化、 [Intel Corporation](https://software.intel.com/articles/intel-sdm)サイト、および、その付録 C を参照してくださいドキュメントです。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__vmx_vmwrite`|X64|

**ヘッダー ファイル** \<intrin.h >

**END Microsoft 固有の仕様**

## <a name="see-also"></a>関連項目

[コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmread](../intrinsics/vmx-vmread.md)