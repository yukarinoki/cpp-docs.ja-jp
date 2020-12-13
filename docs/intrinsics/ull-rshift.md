---
description: '詳細については、次を参照してください: __ull_rshift'
title: __ull_rshift
ms.date: 09/02/2019
f1_keywords:
- __ull_rshift
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
ms.openlocfilehash: 5b819e4a1df8db7b7562023c6acc9dbbd94f7f76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333623"
---
# <a name="__ull_rshift"></a>__ull_rshift

**Microsoft 固有の仕様**

x64 では、最初のパラメーターで指定された64ビット値を、2番目のパラメーターで指定されたビット数だけ右にシフトします。

## <a name="syntax"></a>構文

```C
unsigned __int64 __ull_rshift(
   unsigned __int64 mask,
   int nBit
);
```

### <a name="parameters"></a>パラメーター

*隠す*\
から右にシフトする64ビット整数値。

*nBit*\
からシフトするビット数、x86 の場合は32、x64 の場合はモジュロ64。

## <a name="return-value"></a>戻り値

ビットでシフトされたマスク `nBit` 。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__ull_rshift`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

2番目のパラメーターが x86 の場合は 31 (x64 の場合は 63) を超える場合は、シフトするビット数を決定するために 32 (x64 では 64) が使用されます。 `ull`名前に含まれるはを示し `unsigned long long (unsigned __int64)` ます。

## <a name="example"></a>例

```cpp
// ull_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ull_rshift)

int main()
{
   unsigned __int64 mask = 0x100;
   int nBit = 8;
   mask = __ull_rshift(mask, nBit);
   cout << hex << mask << endl;
}
```

```Output
1
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__ll_lshift](../intrinsics/ll-lshift.md)\
[__ll_rshift](../intrinsics/ll-rshift.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
