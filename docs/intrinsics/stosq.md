---
title: __stosq
ms.date: 11/04/2016
f1_keywords:
- __stosq
helpviewer_keywords:
- rep stosq instruction
- stosq instruction
- __stosq intrinsic
ms.assetid: 3ea28297-4369-4c2d-bf0c-91fa539ce209
ms.openlocfilehash: 48c3e8db2683ee190a23974d12d36fbeef6a0094
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477468"
---
# <a name="stosq"></a>__stosq

**Microsoft 固有の仕様**

ストアの文字列の命令が生成されます (`rep stosq`)。

## <a name="syntax"></a>構文

```
void __stosb( 
   unsigned __int64* Dest, 
   unsigned __int64 Data, 
   size_t Count 
);
```

#### <a name="parameters"></a>パラメーター

*追加先*<br/>
[out]操作の転送先。

*データ*<br/>
[in]格納するデータ。

*カウント*<br/>
[in](クワドワード)。 書き込むのブロックの長さ。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__stosq`|AMD64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

結果は、quadword`Data`のブロックに書き込まれる`Count`で (クワドワード)。、`Dest`文字列。

このルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

```
// stosq.c
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__stosq)

int main()
{
   unsigned __int64 val = 0xFFFFFFFFFFFFI64;
   unsigned __int64 a[10];
   memset(a, 0, sizeof(a));
   __stosq(a+1, val, 2);
   printf("%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);
}
```

## <a name="output"></a>出力

```
0 ffffffffffff ffffffffffff 0
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)