---
description: '詳細については、次を参照してください: __vmx_vmlaunch'
title: __vmx_vmlaunch
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmlaunch
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
ms.openlocfilehash: 3f6596e0644250710491ed90036a651c0725a5f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333545"
---
# <a name="__vmx_vmlaunch"></a>__vmx_vmlaunch

**Microsoft 固有の仕様**

現在の仮想マシン制御構造 (VMCS) を使用して、呼び出し元のアプリケーションを VMX 非ルート操作状態 (VM の入力) に配置します。

## <a name="syntax"></a>構文

```C
unsigned char __vmx_vmlaunch(void);
```

## <a name="return-value"></a>戻り値

|値|意味|
|-----------|-------------|
|0|操作が成功しました。|
|1|現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。|
|2|有効な状態がないため操作は失敗しました。|

## <a name="remarks"></a>解説

アプリケーションでは、 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) または [__vmx_vmresume](../intrinsics/vmx-vmresume.md) のいずれかの機能を使用して、VM の入力操作を実行できます。 [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)関数は、起動状態がである vmcs でのみ使用でき `Clear` ます。また、 [__vmx_vmresume](../intrinsics/vmx-vmresume.md)関数は、起動状態がである vmcs でのみ使用でき `Launched` ます。 そのため、 [__vmx_vmclear](../intrinsics/vmx-vmclear.md) 関数を使用して vmcs の起動状態をに設定 `Clear` した後、最初の vm 入力操作に [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 関数を使用し、後続の vm 入力操作には [__vmx_vmresume](../intrinsics/vmx-vmresume.md) 関数を使用します。

`__vmx_vmlaunch` 関数は `VMLAUNCH` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、 [Intel Corporation](https://software.intel.com/articles/intel-sdm) サイトのドキュメント「IA-32 intel Architecture の Intel Virtualization Technical Specification」 (ドキュメント番号 C97063-002) を検索してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__vmx_vmlaunch`|X64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)\
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)
