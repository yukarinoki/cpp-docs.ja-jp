---
description: '詳細については、次を参照してください: __stosq'
title: __stosq
ms.date: 09/02/2019
f1_keywords:
- __stosq
helpviewer_keywords:
- rep stosq instruction
- stosq instruction
- __stosq intrinsic
ms.assetid: 3ea28297-4369-4c2d-bf0c-91fa539ce209
ms.openlocfilehash: 5fce587c163da18679750c20ec697c489ecf5d90
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143703"
---
# <a name="__stosq"></a>__stosq

**Microsoft 固有の仕様**

ストア文字列命令 () を生成 `rep stosq` します。

## <a name="syntax"></a>構文

```C
void __stosb(
   unsigned __int64* Destination,
   unsigned __int64 Data,
   size_t Count
);
```

### <a name="parameters"></a>パラメーター

*インストール*\
入出力操作の転送先。

*データ*\
から格納するデータ。

*数*\
から書き込む quadwords のブロックの長さ。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__stosq`|AMD64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

結果として、quadword *データ* は、*コピー先* の文字列の *Count* quadwords のブロックに書き込まれます。

このルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

```C
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

```Output
0 ffffffffffff ffffffffffff 0
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
