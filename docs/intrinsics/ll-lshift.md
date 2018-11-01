---
title: __ll_lshift
ms.date: 11/04/2016
f1_keywords:
- __ll_lshift_cpp
- __ll_lshift
helpviewer_keywords:
- ll_lshift intrinsic
- __ll_lshift intrinsic
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
ms.openlocfilehash: 2f0c8f257188dbd3b03ece4269b8c353c7fa26f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625980"
---
# <a name="lllshift"></a>__ll_lshift

**Microsoft 固有の仕様**

指定した 64 ビット値が指定されたビット数だけ左にシフトします。

## <a name="syntax"></a>構文

```
unsigned __int64 __ll_lshift(
   unsigned __int64 Mask,
   int nBit
);
```

#### <a name="parameters"></a>パラメーター

*マスク*<br/>
[in]左にシフトする 64 ビット整数値。

*nBit*<br/>
[in]シフトするビット数。

## <a name="return-value"></a>戻り値

マスクを左にシフト`nBit`ビット。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__ll_lshift`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

64 ビット アーキテクチャを使用して、プログラムをコンパイルするかどうかと`nBit`63 を超えるにシフトするビットの数が`nBit`モジュロ 64 です。 32 ビット アーキテクチャを使用して、プログラムをコンパイルするかどうかと`nBit`31 より大きいにシフトするビットの数が`nBit`32 剰余。

`ll`名前では、操作であるを示します。 `long long` (`__int64`)。

## <a name="example"></a>例

```
// ll_lshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ll_lshift)

int main()
{
   unsigned __int64 Mask = 0x100;
   int nBit = 8;
   Mask = __ll_lshift(Mask, nBit);
   cout << hex << Mask << endl;
}
```

## <a name="output"></a>出力

```
10000
```

**注**左シフト演算の符号なしのバージョンはありません。 これは、ため`__ll_lshift`既に署名されていない入力パラメーターを使用します。 右 shift キーを押しとは異なりはありません左 shift キーを押しへのサインオンのため、結果の最下位ビットは常にシフトした値の符号に関係なく 0 に設定します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__ll_rshift](../intrinsics/ll-rshift.md)<br/>
[__ull_rshift](../intrinsics/ull-rshift.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)