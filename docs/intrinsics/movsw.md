---
title: _ _movsw |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __movsw
dev_langs:
- C++
helpviewer_keywords:
- movsw instruction
- rep movsw instruction
- __movsw intrinsic
ms.assetid: db402ad5-7f0e-449a-b0b0-eea9928d6435
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c8c361fa572435cb7c49320cc1f09abb5f6cd02
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439810"
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

*Source*<br/>
[in]操作のソース。

*カウント*<br/>
[in]コピーする文字数です。

## <a name="requirements"></a>要件

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