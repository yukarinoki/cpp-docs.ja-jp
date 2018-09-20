---
title: _ _stosq |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __stosq
dev_langs:
- C++
helpviewer_keywords:
- rep stosq instruction
- stosq instruction
- __stosq intrinsic
ms.assetid: 3ea28297-4369-4c2d-bf0c-91fa539ce209
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f8aa8c1fd1a5dad6fd70c566cb59bf8dddc4cc3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380140"
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

## <a name="requirements"></a>要件

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