---
description: '詳細については、次を参照してください: __vmx_vmclear'
title: __vmx_vmclear
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmclear
helpviewer_keywords:
- VMCLEAR instruction
- __vmx_vmclear intrinsic
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
ms.openlocfilehash: 2eec5c1189c6a798246a6dabfc731fb0166bc14a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333555"
---
# <a name="__vmx_vmclear"></a>__vmx_vmclear

**Microsoft 固有の仕様**

指定された仮想マシン制御構造 (VMCS) を初期化し、その起動状態をに設定し `Clear` ます。

## <a name="syntax"></a>構文

```C
unsigned char __vmx_vmclear(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>パラメーター

*Vmcsphysのアドレス*\
から消去する VMCS の物理アドレスを格納している64ビットメモリ位置へのポインター。

## <a name="return-value"></a>戻り値

|値|意味|
|-----------|-------------|
|0|操作が成功しました。|
|1|現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。|
|2|有効な状態がないため操作は失敗しました。|

## <a name="remarks"></a>解説

アプリケーションでは、 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) または [__vmx_vmresume](../intrinsics/vmx-vmresume.md) のいずれかの機能を使用して、VM の入力操作を実行できます。 [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)関数は、起動状態がである vmcs でのみ使用でき `Clear` ます。また、 [__vmx_vmresume](../intrinsics/vmx-vmresume.md)関数は、起動状態がである vmcs でのみ使用でき `Launched` ます。 そのため、 [__vmx_vmclear](../intrinsics/vmx-vmclear.md) 関数を使用して、vmcs の起動状態をに設定し `Clear` ます。 最初の VM 入力操作には [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 関数を使用し、後続の vm 入力操作には [__vmx_vmresume](../intrinsics/vmx-vmresume.md) 関数を使用します。

`__vmx_vmclear` 関数は `VMCLEAR` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、 [Intel Corporation](https://software.intel.com/articles/intel-sdm) サイトのドキュメント「IA-32 intel Architecture の Intel Virtualization Technical Specification」 (ドキュメント番号 C97063-002) を検索してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__vmx_vmclear`|X64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)\
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)
