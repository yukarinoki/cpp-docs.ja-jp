---
description: '詳細については、次を参照してください: __vmx_on'
title: __vmx_on
ms.date: 09/02/2019
f1_keywords:
- __vmx_on
helpviewer_keywords:
- VMXON instruction
- __vmx_on intrinsic
ms.assetid: 16804991-6a75-4adf-8ec2-bc95acfa4801
ms.openlocfilehash: a1e9171fe64a239b592f0d27ec49d4159b46523d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333578"
---
# <a name="__vmx_on"></a>__vmx_on

**Microsoft 固有の仕様**

プロセッサの仮想マシン拡張機能 (VMX) 操作をアクティブにします。

## <a name="syntax"></a>構文

```C
unsigned char __vmx_on(
   unsigned __int64 *VmsSupportPhysicalAddress
);
```

### <a name="parameters"></a>パラメーター

*VmsSupportPhysicalAddress*\
から仮想マシンの制御構造 (VMCS) を指す64ビットの物理アドレスへのポインター。

## <a name="return-value"></a>戻り値

|値|意味|
|-----------|-------------|
|0|操作が成功しました。|
|1|現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。|
|2|有効な状態がないため操作は失敗しました。|

## <a name="remarks"></a>解説

関数は、 `__vmx_on` マシン命令に対応し `VMXON` ます。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、 [Intel Corporation](https://software.intel.com/articles/intel-sdm) サイトのドキュメント「IA-32 intel Architecture の Intel Virtualization Technical Specification」 (ドキュメント番号 C97063-002) を検索してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__vmx_on`|X64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
