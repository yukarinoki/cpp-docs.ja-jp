---
title: __rdtsc
ms.date: 11/04/2016
f1_keywords:
- __rdtsc
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
ms.openlocfilehash: 6f30be3340ae1be237bb2f8a008a8cb60c7351f0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036839"
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

## <a name="requirements"></a>必要条件

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

**END Microsoft 固有の仕様**

## <a name="see-also"></a>関連項目

[コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)