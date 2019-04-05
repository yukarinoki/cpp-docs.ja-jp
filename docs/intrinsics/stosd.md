---
title: __stosd
ms.date: 11/04/2016
f1_keywords:
- __stosd
helpviewer_keywords:
- stosd instruction
- rep stosd instruction
- __stosd intrinsic
ms.assetid: 03104247-1cea-49f6-b6f8-287917bf5680
ms.openlocfilehash: 43a0efcfb94b7e53dacec16caccdacf86a96f5bb
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032168"
---
# <a name="stosd"></a>__stosd

**Microsoft 固有の仕様**

ストアの文字列の命令が生成されます (`rep stosd`)。

## <a name="syntax"></a>構文

```
void __stosd(
   unsigned long* Dest,
   unsigned long Data,
   size_t Count
);
```

#### <a name="parameters"></a>パラメーター

*追加先*<br/>
[out]操作の転送先。

*データ*<br/>
[in]格納するデータ。

*カウント*<br/>
[in]書き込むダブルワードのブロックの長さ。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__stosd`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

結果はダブルワード`Data`のブロックに書き込まれる`Count`によって示されるメモリ位置にダブルワード`Dest`します。

このルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

```
// stosd.c
// processor: x86, x64

#include <stdio.h>
#include <memory.h>
#include <intrin.h>

#pragma intrinsic(__stosd)

int main()
{
    unsigned long val = 99999;
    unsigned long a[10];

    memset(a, 0, sizeof(a));
    __stosd(a+1, val, 2);

printf_s( "%u %u %u %u",
              a[0], a[1], a[2], a[3]);
}
```

```Output
0 99999 99999 0
```

**END Microsoft 固有の仕様**

## <a name="see-also"></a>関連項目

[コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)