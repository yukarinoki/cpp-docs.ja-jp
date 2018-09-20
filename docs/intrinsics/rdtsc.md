---
title: _ _rdtsc |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __rdtsc
dev_langs:
- C++
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d10bf2392d7e469f8f9a8a113b96e0cf2be88a50
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434532"
---
# <a name="rdtsc"></a>__rdtsc

**Microsoft 固有の仕様**

生成、`rdtsc`命令で、プロセッサのタイムスタンプを返します。 プロセッサのタイムスタンプは、最後のリセット以降のクロック サイクル数を記録します。

## <a name="syntax"></a>構文

```
unsigned __int64 __rdtsc();
```

## <a name="return-value"></a>戻り値

ティック カウントを表す 64 ビット符号なし整数。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__rdtsc`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

このルーチンは組み込みとしてのみ使用できます。

この世代のハードウェアで TSC 値の解釈は、x64 の以前のバージョンとは異なります。 詳細についてはハードウェアのマニュアルを参照してください。

## <a name="example"></a>例

```
// rdtsc.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__rdtsc)

int main()
{
    unsigned __int64 i;
    i = __rdtsc();
    printf_s("%I64d ticks\n", i);
}
```

```Output
3363423610155519 ticks
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)