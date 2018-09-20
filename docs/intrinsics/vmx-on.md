---
title: _ _vmx_on |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_on
dev_langs:
- C++
helpviewer_keywords:
- VMXON instruction
- __vmx_on intrinsic
ms.assetid: 16804991-6a75-4adf-8ec2-bc95acfa4801
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 21ac0eb53b75aece9d717b85b9625a69741a2be9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379760"
---
# <a name="vmxon"></a>__vmx_on

**Microsoft 固有の仕様**

プロセッサの仮想マシン拡張機能 (VMX) 操作をアクティブにします。

## <a name="syntax"></a>構文

```
unsigned char __vmx_on(
   unsigned __int64 *VmsSupportPhysicalAddress
);
```

#### <a name="parameters"></a>パラメーター

*VmsSupportPhysicalAddress*<br/>
[in]仮想マシンの制御構造 (VMCS) を指す 64 ビットの物理アドレスへのポインター。

## <a name="return-value"></a>戻り値

|[値]|説明|
|-----------|-------------|
|0|操作が成功しました。|
|1|現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。|
|2|有効な状態がないため操作は失敗しました。|

## <a name="remarks"></a>Remarks

`__vmx_on`関数に対応する、`VMXON`マシン語命令。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、検索、ドキュメント、「Intel 仮想化技術仕様 ia-32 Intel アーキテクチャ向け、」で番号 C97063-002、文書化、 [Intel Corporation](https://software.intel.com/en-us/articles/intel-sdm)サイト。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__vmx_on`|X64|

**ヘッダー ファイル** \<intrin.h >

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)