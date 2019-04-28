---
title: __ll_rshift
ms.date: 11/04/2016
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
ms.openlocfilehash: e39f8fe797467569077dd24baf49670607915107
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263361"
---
# <a name="llrshift"></a>__ll_rshift

**Microsoft 固有の仕様**

右側の最初のパラメーターで指定した 64 ビット値を 2 番目のパラメーターで指定されたビット数だけシフトします。

## <a name="syntax"></a>構文

```
__int64 __ll_rshift(
   __int64 Mask,
   int nBit
);
```

#### <a name="parameters"></a>パラメーター

*マスク*<br/>
[in]右にシフトする 64 ビット整数値。

*nBit*<br/>
[in]モジュロ x64 で 64 および x86 上で 32 剰余をシフトするビット数。

## <a name="return-value"></a>戻り値

マスクがずれる`nBit`ビット。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__ll_rshift`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

2 番目のパラメーターが x64 (x86 上で 32) で 64 よりも大きい場合は、その数は、シフトするビットの数を決定する、モジュロ 64 (x86 上で 32) 取得されます。 `ll`プレフィックスは、の操作であることを示します`long long`、もう 1 つの名前`__int64`、64 ビット符号付き整数型。

## <a name="example"></a>例

```
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

```
ffffffffffffff00
- 100
fffffffffffffff0
- 10
```

**注**場合`_ull_rshift`が使用すると、右にシフトした値の MSB いたでしょう 0 の場合、目的の結果は取得できていない場合は負の値をします。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__ll_lshift](../intrinsics/ll-lshift.md)<br/>
[__ull_rshift](../intrinsics/ull-rshift.md)