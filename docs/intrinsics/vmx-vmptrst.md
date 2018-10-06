---
title: _ _vmx_vmptrst |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmptrst
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmptrst intrinsic
- VMPTRST instruction
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f9cd2ebdbcf2ad2feb3b66412fbcd5687e85dce
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820569"
---
# <a name="vmxvmptrst"></a>__vmx_vmptrst

**Microsoft 固有の仕様**

指定したアドレスには、現在仮想マシンの制御構造 (VMCS) へのポインターを格納します。

## <a name="syntax"></a>構文

```
void __vmx_vmptrst( 
   unsigned __int64 *VmcsPhysicalAddress 
);
```

#### <a name="parameters"></a>パラメーター

[in] *`VmcsPhysicalAddress`現在 VMCS ポインターが格納されているアドレスです。

## <a name="remarks"></a>Remarks

VMCS ポインターは、64 ビットの物理アドレスです。

`__vmx_vmptrst`関数は、`VMPTRST`マシン語命令。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、検索、ドキュメント、「Intel 仮想化技術仕様 ia-32 Intel アーキテクチャ向け、」で番号 C97063-002、文書化、 [Intel Corporation](https://software.intel.com/articles/intel-sdm)サイト。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__vmx_vmptrst`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)