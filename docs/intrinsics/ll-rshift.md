---
description: '詳細については、次を参照してください: __ll_rshift'
title: __ll_rshift
ms.date: 09/02/2019
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
ms.openlocfilehash: 567228431104bdde34cc0a5c5f41f0217515a337
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167748"
---
# <a name="__ll_rshift"></a>__ll_rshift

**Microsoft 固有の仕様**

最初のパラメーターで指定された64ビット値を、2番目のパラメーターで指定されたビット数だけ右にシフトします。

## <a name="syntax"></a>構文

```C
__int64 __ll_rshift(
   __int64 Mask,
   int nBit
);
```

### <a name="parameters"></a>パラメーター

*隠す*\
から右にシフトする64ビット整数値。

*nBit*\
からシフトするビット数、x64 の場合は64、x86 の場合はモジュロ32。

## <a name="return-value"></a>戻り値

ビットでシフトされたマスク `nBit` 。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__ll_rshift`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

2番目のパラメーターが x64 の 64 (x86 の場合は 32) を超える場合は、シフトするビット数を決定するために、その数値が 64 (x86 の場合は 32) によって取得されます。 プレフィックスは、 `ll` が操作であることを示します。これは、 **`long long`** **`__int64`** 64 ビットの符号付き整数型である別の名前です。

## <a name="example"></a>例

```cpp
// ll_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ll_rshift)

int main()
{
   __int64 Mask = - 0x100;
   int nBit = 4;
   cout << hex << Mask << endl;
   cout << " - " << (- Mask) << endl;
   Mask = __ll_rshift(Mask, nBit);
   cout << hex << Mask << endl;
   cout << " - " << (- Mask) << endl;
}
```

## <a name="output"></a>出力

```Output
ffffffffffffff00
- 100
fffffffffffffff0
- 10
```

> [!NOTE]
> `_ull_rshift`が使用されている場合は、右シフトされた値の MSB が0になったため、目的の結果が負の値の場合に取得されていません。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__ll_lshift](../intrinsics/ll-lshift.md)\
[__ull_rshift](../intrinsics/ull-rshift.md)
