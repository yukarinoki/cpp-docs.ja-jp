---
title: _BitScanForward、_BitScanForward64
ms.date: 11/04/2016
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
ms.openlocfilehash: 8b09aeee485611ddd20d51b4c1e36ec98c03c26e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022568"
---
# <a name="bitscanforward-bitscanforward64"></a>_BitScanForward、_BitScanForward64

**Microsoft 固有の仕様**

マスク データの最下位ビット (LSB) から最上位ビット (MSB) に向かって設定済みビット (1) を検索します。

## <a name="syntax"></a>構文

```
unsigned char _BitScanForward(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanForward64(
   unsigned long * Index,
   unsigned __int64 Mask
);
```

#### <a name="parameters"></a>パラメーター

*Index*<br/>
[out]見つかった最初のビット セット (1) のビット位置が読み込まれます。

*マスク*<br/>
[in]検索する 32 ビットまたは 64 ビット値。

## <a name="return-value"></a>戻り値

マスクが 0 の場合は 0。それ以外の場合は 0 以外。

## <a name="remarks"></a>Remarks

設定済みビットが見つかった場合は、最初に見つかった設定済みビットのビット位置が最初のパラメーターで返されます。 設定済みビットが見つからない場合は 0 が返されます。それ以外の場合は 1 が返されます。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`_BitScanForward`|x86、ARM、x64|
|`_BitScanForward64`|ARM、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="example"></a>例

```
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

## <a name="input"></a>入力

```
12
```

## <a name="sample-output"></a>出力例

```
Enter a positive integer as the mask:
Mask: 12 Index: 2
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)