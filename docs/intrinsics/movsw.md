---
description: '詳細については、次を参照してください: __movsw'
title: __movsw
ms.date: 09/02/2019
f1_keywords:
- __movsw
helpviewer_keywords:
- movsw instruction
- rep movsw instruction
- __movsw intrinsic
ms.assetid: db402ad5-7f0e-449a-b0b0-eea9928d6435
ms.openlocfilehash: 500a2bc3af83887cdd5d65501695c9db60ef60f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119030"
---
# <a name="__movsw"></a>__movsw

**Microsoft 固有の仕様**

Move String ( `rep movsw` ) 命令を生成します。

## <a name="syntax"></a>構文

```C
void __movsw(
   unsigned short* Destination,
   unsigned short* Source,
   size_t Count
);
```

### <a name="parameters"></a>パラメーター

*インストール*\
入出力操作の転送先。

*電源*\
から操作のソース。

*数*\
からコピーする単語数。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__movsw`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

結果として、*ソース* によって参照されている最初の *カウント* 単語が、コピー *先* の文字列にコピーされます。

このルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

```cpp
// movsw.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsw)

int main()
{
    unsigned short s1[10];
    unsigned short s2[10] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
    __movsw(s1, s2, 10);

    for (int i = 0; i < 10; i++)
        printf_s("%d ", s1[i]);
    printf_s("\n");
}
```

```Output
0 1 2 3 4 5 6 7 8 9
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
