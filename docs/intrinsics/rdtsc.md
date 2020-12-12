---
description: '詳細については、次を参照してください: __rdtsc'
title: __rdtsc
ms.date: 09/02/2019
f1_keywords:
- __rdtsc
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
ms.openlocfilehash: 930c8fbd0ae762c8674a85e379899bc4fe4d3394
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257512"
---
# <a name="__rdtsc"></a>__rdtsc

**Microsoft 固有の仕様**

プロセッサの `rdtsc` タイムスタンプを返す命令を生成します。 プロセッサのタイムスタンプには、前回のリセットからのクロックサイクル数が記録されます。

## <a name="syntax"></a>構文

```C
unsigned __int64 __rdtsc();
```

## <a name="return-value"></a>戻り値

ティック数を表す64ビット符号なし整数。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__rdtsc`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

このルーチンは、組み込みとしてのみ使用できます。

新しい世代のハードウェアでの TSC 値の解釈は、以前のバージョンの x64 の場合と異なります。 詳細については、ハードウェアのマニュアルを参照してください。

## <a name="example"></a>例

```cpp
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
