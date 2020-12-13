---
description: '詳細については、次を参照してください: __vmx_vmresume'
title: __vmx_vmresume
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmresume
helpviewer_keywords:
- __vmx_vmresume intrinsic
- VMRESUME instruction
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
ms.openlocfilehash: 35c1ca7eeca847b14d16c451752a186c63a59749
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343779"
---
# <a name="__vmx_vmresume"></a>__vmx_vmresume

**Microsoft 固有の仕様**

現在の仮想マシンの制御構造 (VMCS) を使用することで、VMX の非ルート操作を再開します。

## <a name="syntax"></a>構文

```C
unsigned char __vmx_vmresume(
   void);
```

## <a name="return-value"></a>戻り値

|値|意味|
|-----------|-------------|
|0|操作が成功しました。|
|1|現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。|
|2|有効な状態がないため操作は失敗しました。|

## <a name="remarks"></a>解説

アプリケーションは、 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 関数または `__vmx_vmresume` 関数を使用して VM 入力操作を実行できます。 `__vmx_vmlaunch` 関数は起動状態が `Clear`の VMCS でのみ使用できます。 `__vmx_vmresume` 関数は起動状態が `Launched`の VMCS でのみ使用できます。 そのため、 [__vmx_vmclear](../intrinsics/vmx-vmclear.md) 関数を使用して VMCS の起動状態を `Clear`に設定し、その後で、最初の VM 入力操作に `__vmx_vmlaunch` 関数を使用し、後続の VM 入力操作に `__vmx_vmresume` 関数を使用します。

`__vmx_vmresume` 関数は `VMRESUME` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、 [Intel Corporation](https://software.intel.com/articles/intel-sdm) のサイトで、PDF ドキュメント「IA-32 Intel アーキテクチャ向け Intel 仮想化テクノロジ仕様」(ドキュメント番号 C97063-002) を参照してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__vmx_vmresume`|X64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)\
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)
