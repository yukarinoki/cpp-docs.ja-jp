---
description: '詳細については、次を参照してください: _rotr8、_rotr16'
title: _rotr8、_rotr16
ms.date: 09/02/2019
f1_keywords:
- _rotr16
- _rotr8
helpviewer_keywords:
- _rotr8 intrinsic
- _rotr16 intrinsic
ms.assetid: dfbd2c82-82b4-427a-ad52-51609027ebff
ms.openlocfilehash: 95908956fe34b654c3602f27b495eb58a0b8f8c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307042"
---
# <a name="_rotr8-_rotr16"></a>_rotr8、_rotr16

**Microsoft 固有の仕様**

指定したビット位置の数だけ、最下位ビット (LSB) に向かって入力値を右に回転します。

## <a name="syntax"></a>構文

```C
unsigned char _rotr8(
   unsigned char value,
   unsigned char shift
);
unsigned short _rotr16(
   unsigned short value,
   unsigned char shift
);
```

### <a name="parameters"></a>パラメーター

*数値*\
から回転する値。

*転換*\
から回転するビット数。

## <a name="return-value"></a>戻り値

回転後の値。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`_rotr8`|x86、ARM、x64、ARM64|
|`_rotr16`|x86、ARM、x64、ARM64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

右シフト演算とは異なり、右の回転を実行すると、下位にある下位ビットが上位ビット位置に移動されます。

## <a name="example"></a>例

```cpp
// rotr.cpp
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_rotr8, _rotr16)

int main()
{
    unsigned char c = 'A', c1, c2;

    for (int i = 0; i < 8; i++)
    {
       printf_s("Rotating 0x%x right by %d bits gives 0x%x\n", c,
                i, _rotr8(c, i));
    }

    unsigned short s = 0x12;
    int nBit = 10;

    printf_s("Rotating unsigned short 0x%x right by %d bits "
             "gives 0x%x\n",
            s, nBit, _rotr16(s, nBit));
}
```

```Output
Rotating 0x41 right by 0 bits gives 0x41
Rotating 0x41 right by 1 bits gives 0xa0
Rotating 0x41 right by 2 bits gives 0x50
Rotating 0x41 right by 3 bits gives 0x28
Rotating 0x41 right by 4 bits gives 0x14
Rotating 0x41 right by 5 bits gives 0xa
Rotating 0x41 right by 6 bits gives 0x5
Rotating 0x41 right by 7 bits gives 0x82
Rotating unsigned short 0x12 right by 10 bits gives 0x480
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_rotl8、_rotl16](../intrinsics/rotl8-rotl16.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
