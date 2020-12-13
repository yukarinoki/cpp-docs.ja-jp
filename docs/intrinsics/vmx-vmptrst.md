---
description: '詳細については、次を参照してください: __vmx_vmptrst'
title: __vmx_vmptrst
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmptrst
helpviewer_keywords:
- __vmx_vmptrst intrinsic
- VMPTRST instruction
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
ms.openlocfilehash: 216da453acf5c04e4189271185567841327571ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333521"
---
# <a name="__vmx_vmptrst"></a>__vmx_vmptrst

**Microsoft 固有の仕様**

指定したアドレスにある現在の仮想マシン制御構造 (VMCS) へのポインターを格納します。

## <a name="syntax"></a>構文

```C
void __vmx_vmptrst(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>パラメーター

*Vmcsphysのアドレス*\
から現在の VMCS ポインターが格納されているアドレス。

## <a name="remarks"></a>解説

VMCS ポインターは、64ビットの物理アドレスです。

`__vmx_vmptrst` 関数は `VMPTRST` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、 [Intel Corporation](https://software.intel.com/articles/intel-sdm) サイトのドキュメント「IA-32 intel Architecture の Intel Virtualization Technical Specification」 (ドキュメント番号 C97063-002) を検索してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__vmx_vmptrst`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)
