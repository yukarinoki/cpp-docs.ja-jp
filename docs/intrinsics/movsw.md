---
title: __movsw
ms.date: 11/04/2016
f1_keywords:
- __movsw
helpviewer_keywords:
- movsw instruction
- rep movsw instruction
- __movsw intrinsic
ms.assetid: db402ad5-7f0e-449a-b0b0-eea9928d6435
ms.openlocfilehash: 4bb8a6411c3700b3338fb7d5bc76884f84bb2413
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453616"
---
# <a name="movsw"></a>__movsw

**Microsoft 固有の仕様**

移動の文字列が生成されます (`rep movsw`) 命令。

## <a name="syntax"></a>構文

```
void __movsw( 
   unsigned short* Dest, 
   unsigned short* Source, 
   size_t Count 
);
```

#### <a name="parameters"></a>パラメーター

*追加先*<br/>
[out]操作の転送先。

*ソース*<br/>
[in]操作のソース。

*カウント*<br/>
[in]コピーする文字数です。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__movsw`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

その結果、最初の`Count`によって示される単語`Source`にコピーされます、`Dest`文字列。

このルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

```
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