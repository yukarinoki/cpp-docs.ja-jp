---
title: __vmx_vmptrst
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmptrst
helpviewer_keywords:
- __vmx_vmptrst intrinsic
- VMPTRST instruction
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
ms.openlocfilehash: 5ef02dd4401e0c10a84be008d7cb25841e0359cd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59029513"
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

### <a name="parameters"></a>パラメーター

*VmcsPhysicalAddress*<br/>
[in]現在 VMCS ポインターが格納されているアドレスです。

## <a name="remarks"></a>Remarks

VMCS ポインターは、64 ビットの物理アドレスです。

`__vmx_vmptrst` 関数は `VMPTRST` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、検索、ドキュメント、「Intel 仮想化技術仕様 ia-32 Intel アーキテクチャ向け、」で番号 C97063-002、文書化、 [Intel Corporation](https://software.intel.com/articles/intel-sdm)サイト。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__vmx_vmptrst`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)