---
description: '詳細については、次を参照してください: _BitScanReverse、_BitScanReverse64'
title: _BitScanReverse、_BitScanReverse64
ms.date: 09/02/2019
f1_keywords:
- _BitScanReverse64
- _BitScanReverse_cpp
- _BitScanReverse
- _BitScanReverse64_cpp
helpviewer_keywords:
- bsr instruction
- _BitScanReverse intrinsic
- BitScanReverse intrinsic
ms.assetid: 2520a207-af8b-4aad-9ae7-831abeadf376
ms.openlocfilehash: 1a535dcc95f9fbf791de3ecd2c2d54eddcc0399c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337208"
---
# <a name="_bitscanreverse-_bitscanreverse64"></a>_BitScanReverse、_BitScanReverse64

**Microsoft 固有の仕様**

マスク データの最上位ビット (MSB) から最下位ビット (LSB) に向かって設定済みビット (1) を検索します。

## <a name="syntax"></a>構文

```C
unsigned char _BitScanReverse(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanReverse64(
   unsigned long * Index,
   unsigned __int64 Mask
);
```

### <a name="parameters"></a>パラメーター

*[インデックス]* \
入出力見つかった最初のセットビット (1) のビット位置を使用して読み込まれます。

*隠す*\
から検索する32ビットまたは64ビットの値。

## <a name="return-value"></a>戻り値

`Index` が設定された場合は 0 以外、設定済みビットが見つからなかった場合は 0。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|ヘッダー|
|---------------|------------------|------------|
|`_BitScanReverse`|x86、ARM、x64、ARM64|\<intrin.h>|
|`_BitScanReverse64`|ARM64、x64|\<intrin.h>|

## <a name="example"></a>例

```cpp
// BitScanReverse.cpp
// compile with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_BitScanReverse)

int main()
{
   unsigned long mask = 0x1000;
   unsigned long index;
   unsigned char isNonzero;

   cout << "Enter a positive integer as the mask: " << flush;
   cin >> mask;
   isNonzero = _BitScanReverse(&index, mask);
   if (isNonzero)
   {
      cout << "Mask: " << mask << " Index: " << index << endl;
   }
   else
   {
      cout << "No set bits found.  Mask is zero." << endl;
   }
}
```

```Input
12
```

```Output
Enter a positive integer as the mask:
Mask: 12 Index: 3
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
