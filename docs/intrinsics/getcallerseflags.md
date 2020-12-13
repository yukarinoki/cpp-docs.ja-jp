---
description: '詳細については、次を参照してください: __getcallerseflags'
title: __getcallerseflags
ms.date: 09/02/2019
f1_keywords:
- _getcallerseflags
- _getcallerseflags_cpp
helpviewer_keywords:
- _getcallerseflags intrinsic
ms.assetid: 2386596f-33aa-4cc7-b026-5a834637270a
ms.openlocfilehash: bc73ca965f61ee4b5291c48f9680d4aa2f1774a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337000"
---
# <a name="__getcallerseflags"></a>__getcallerseflags

**Microsoft 固有の仕様**

呼び出し元のコンテキストから EFLAGS 値を返します。

## <a name="syntax"></a>構文

```C
unsigned int __getcallerseflags(void);
```

## <a name="return-value"></a>戻り値

呼び出し元のコンテキストからの EFLAGS 値。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__getcallerseflags`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

このルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

```cpp
// getcallerseflags.cpp
// processor: x86, x64

#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__getcallerseflags)

unsigned int g()
{
    unsigned int EFLAGS = __getcallerseflags();
    printf_s("EFLAGS 0x%x\n", EFLAGS);
    return EFLAGS;
}
unsigned int f()
{
    return g();
}

int main()
{
    unsigned int i;
    i = f();
    i = g();
    return 0;
}
```

```Output
EFLAGS 0x202
EFLAGS 0x206
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
