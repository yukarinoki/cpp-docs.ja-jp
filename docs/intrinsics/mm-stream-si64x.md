---
title: _mm_stream_si64x |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_stream_si64x
dev_langs:
- C++
helpviewer_keywords:
- movnti instruction
- _mm_stream_si64x intrinsic
ms.assetid: 114c2cd0-085f-41aa-846e-87bdd56c9ee7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 568f1c32553a07de7f1ac7bf8ad3d0652e26d437
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417658"
---
# <a name="mmstreamsi64x"></a>_mm_stream_si64x

**Microsoft 固有の仕様**

MOVNTI 命令を生成します。 において、データを書き込む`Source`で指定されたメモリ位置へ`Dest`キャッシュの汚染なし。

## <a name="syntax"></a>構文

```
void _mm_stream_si64x( 
   __int64 * Dest, 
   __int64 Source 
);
```

#### <a name="parameters"></a>パラメーター

*追加先*<br/>
[out]ソース データを書き込む場所へのポインター。

*Source*<br/>
[in]書き込むデータ。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`_mm_stream_si64x`|X64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

このルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

```C
// _mm_stream_si64x.c
// processor: x64

#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_mm_stream_si64x)

int main()
{
    __int64 val = 0xFFFFFFFFFFFFI64;
    __int64 a[10];

    memset(a, 0, sizeof(a));
    _mm_stream_si64x(a+1, val);
    printf_s( "%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);
}
```

```Output
0 ffffffffffff 0 0
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)