---
description: '詳細については、次を参照してください: _BitScanForward、_BitScanForward64'
title: _BitScanForward、_BitScanForward64
ms.date: 09/02/2019
f1_keywords:
- _BitScanForward
- _BitScanForward_cpp
- _BitScanForward64_cpp
- _BitScanForward64
helpviewer_keywords:
- _BitScanForward intrinsic
- bsf instruction
- BitScanForward intrinsic
ms.assetid: 405e60fb-0815-42a7-9b02-6fc035122203
ms.openlocfilehash: 182f22b5350fcad7c3da9a0d6f6df36c0871a3e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337231"
---
# <a name="_bitscanforward-_bitscanforward64"></a>_BitScanForward、_BitScanForward64

**Microsoft 固有の仕様**

マスク データの最下位ビット (LSB) から最上位ビット (MSB) に向かって設定済みビット (1) を検索します。

## <a name="syntax"></a>構文

```C
unsigned char _BitScanForward(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanForward64(
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

マスクが 0 の場合は 0。それ以外の場合は 0 以外。

## <a name="remarks"></a>解説

設定済みビットが見つかった場合は、最初に見つかった設定済みビットのビット位置が最初のパラメーターで返されます。 設定済みビットが見つからない場合は 0 が返されます。それ以外の場合は 1 が返されます。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`_BitScanForward`|x86、ARM、x64、ARM64|
|`_BitScanForward64`|ARM64、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="example"></a>例

```cpp
// BitScanForward.cpp
// compile with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_BitScanForward)

int main()
{
   unsigned long mask = 0x1000;
   unsigned long index;
   unsigned char isNonzero;

   cout << "Enter a positive integer as the mask: " << flush;
   cin >> mask;
   isNonzero = _BitScanForward(&index, mask);
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
Mask: 12 Index: 2
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
