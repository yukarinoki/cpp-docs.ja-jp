---
title: __vmx_vmlaunch
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmlaunch
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
ms.openlocfilehash: 37f3a39ee7b0d4d24f26fab2347ac9fca020ec47
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037052"
---
# <a name="vmxvmlaunch"></a>__vmx_vmlaunch

**Microsoft 固有の仕様**

現在の仮想マシンの制御構造 (VMCS) を使用して、VMX の非ルート操作の状態 (入力 VM) では、呼び出し元のアプリケーションを配置します。

## <a name="syntax"></a>構文

```
unsigned char __vmx_vmlaunch(
   void);
```

## <a name="return-value"></a>戻り値

|[値]|説明|
|-----------|-------------|
|0|操作が成功しました。|
|1|現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。|
|2|有効な状態がないため操作は失敗しました。|

## <a name="remarks"></a>Remarks

アプリケーションは、いずれかを使用して VM 入力操作を実行できます、 [_ _vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)または[_ _vmx_vmresume](../intrinsics/vmx-vmresume.md)関数。 [_ _Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)関数は、起動状態が VMCS でのみ使用できます`Clear`、および[_ _vmx_vmresume](../intrinsics/vmx-vmresume.md)関数は、起動状態が VMCS でのみ使用できます`Launched`します。 そのため、使用、 [_ _vmx_vmclear](../intrinsics/vmx-vmclear.md)に VMCS の起動状態を設定する関数`Clear`、しを使用して、 [_ _vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)最初の VM 入力操作と、関数[_ _vmx_vmresume](../intrinsics/vmx-vmresume.md)関数の後続の VM 入力操作。

`__vmx_vmlaunch` 関数は `VMLAUNCH` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、検索、ドキュメント、「Intel 仮想化技術仕様 ia-32 Intel アーキテクチャ向け、」で番号 C97063-002、文書化、 [Intel Corporation](https://software.intel.com/articles/intel-sdm)サイト。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__vmx_vmlaunch`|X64|

**ヘッダー ファイル** \<intrin.h >

**END Microsoft 固有の仕様**

## <a name="see-also"></a>関連項目

[コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)<br/>
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)