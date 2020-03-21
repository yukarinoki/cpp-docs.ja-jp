---
title: __ull_rshift
ms.date: 09/02/2019
f1_keywords:
- __ull_rshift
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
ms.openlocfilehash: bf9fe7775cee1c774c097a1b6bd371721c9fa34f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80074988"
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

*マスク*\
から右にシフトする64ビット整数値。

*Nbit*\
からシフトするビット数、x86 の場合は32、x64 の場合はモジュロ64。

## <a name="return-value"></a>戻り値

`nBit` ビットでシフトしたマスク。

## <a name="requirements"></a>必要条件

|Intrinsic|Architecture|
|---------------|------------------|
|`__ull_rshift`|x86、x64|

**ヘッダーファイル**\<に存在します。 h >

## <a name="remarks"></a>解説

2番目のパラメーターが x86 の場合は 31 (x64 の場合は 63) を超える場合は、シフトするビット数を決定するために 32 (x64 では 64) が使用されます。 名前の `ull` は `unsigned long long (unsigned __int64)`を示します。

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

## <a name="see-also"></a>参照

[__ll_lshift](../intrinsics/ll-lshift.md)\
[__ll_rshift](../intrinsics/ll-rshift.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
