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
ms.openlocfilehash: 5f058eaf6587b74f5a75044416d23ac6b64fb415
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582066"
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

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)