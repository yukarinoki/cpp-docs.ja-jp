---
title: _mm_insert_si64、_mm_inserti_si64
ms.date: 11/04/2016
f1_keywords:
- _mm_inserti_si64
- _mm_insert_si64
helpviewer_keywords:
- insertq instruction
- _mm_insert_si64 intrinsic
- _mm_inserti_si64 intrinsic
ms.assetid: 897a4b36-8b08-4b00-a18f-7850f5732d7d
ms.openlocfilehash: 062e7e56de16d8e8a18101dec0a8e9766e02967f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631035"
---
# <a name="mminsertsi64-mminsertisi64"></a>_mm_insert_si64、_mm_inserti_si64

**Microsoft 固有の仕様**

生成、 `insertq` 2 番目のオペランドからのビットを最初のオペランドに挿入する命令です。

## <a name="syntax"></a>構文

```
__m128i _mm_insert_si64(
   __m128i Source1,
   __m128i Source2
);
__m128i _mm_inserti_si64(
   __m128i Source1,
   __m128i Source2
   int Length,
   int Index
);
```

#### <a name="parameters"></a>パラメーター

*Source1*<br/>
[in]入力データの下位 64 ビット フィールドが挿入されるのでは、128 ビット フィールドです。

*Source2*<br/>
[in]その下位ビットに挿入するデータは、128 ビット フィールドです。  `_mm_insert_si64`もフィールド記述子の上位ビットに含まれています。

*長さ*<br/>
[in]整数定数を挿入するフィールドの長さを指定します。

*Index*<br/>
[in]データが挿入されるフィールドの最下位ビットのインデックスを指定する整数の定数。

## <a name="return-value"></a>戻り値

128 ビット フィールドの下位 64 ビットの元の下位 64 ビットを含む`Source1`指定したビット フィールドの下位ビットを置き換えて`Source2`します。 戻り値の上位 64 ビットは、定義されていません。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`_mm_insert_si64`|SSE4a|
|`_mm_inserti_si64`|SSE4a|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

この組み込みを生成、`insertq`からビットを挿入する命令`Source2`に`Source1`します。 この 2 つのバージョンがある組み込み: `_mm_inserti_si64`、即時のバージョンと`_mm_insert_si64`緊急であります。  各バージョンでは、Source2 から指定された長さのビット フィールドを抽出し、Source1 に挿入します。  抽出されたビットは、Source2 の最下位ビットです。  これらのビットが挿入されるフィールド Source1 は、長さと、その最下位ビットのインデックスによって定義されます。  Mod 64 を長さとインデックスの値が表示されます、-1 から 127 文字の両方が 63 として解釈されます。 (縮小) のビットのインデックスと (縮小) フィールドの長さの合計を 64 を超える場合は、結果は定義されていません。 フィールド長に 0 の値は、64 として解釈されます。  場合、フィールドの長さとビットのインデックスの両方で 0 ビット 63:0`Source2`が挿入`Source1`します。  フィールドの長さが 0 ビットのインデックスが 0 でない場合、結果は定義されていません。

_Mm_insert_si64、呼び出しでは、フィールドの長さは Source2 と bits 69:64 内のインデックスのビット 77:72 に含まれます。

呼び出す場合`_mm_inserti_si64`コンパイラがそれらの値を XMM レジスタにパックし、呼び出すコードを生成、コンパイラは、整数定数である判断できない引数で`_mm_insert_si64`します。

ハードウェアのサポートを決定する、`insertq`命令の呼び出し、`__cpuid`で組み込み`InfoType=0x80000001`のビット 6 をチェックし、`CPUInfo[2] (ECX)`します。 このビットは、それ以外の場合、命令がサポートされている場合は 1、0 になります。 `insertq`命令が搭載されていないハードウェア上でこの組み込み関数を呼び出した場合、その結果は保証されません。

## <a name="example"></a>例

```
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

union {
    __m128i m;
    unsigned __int64 ui64[2];
} source1, source2, source3, result1, result2, result3;

int
main()
{

    __int64 mask;

    source1.ui64[0] = 0xffffffffffffffffll;
    source2.ui64[0] = 0xfedcba9876543210ll;
    source2.ui64[1] = 0xc10;
    source3.ui64[0] = source2.ui64[0];

    result1.m = _mm_insert_si64 (source1.m, source2.m);
    result2.m = _mm_inserti_si64(source1.m, source3.m, 16, 12);
    mask = 0xffff << 12;
    mask = ~mask;
    result3.ui64[0] = (source1.ui64[0] & mask) |
                      ((source2.ui64[0] & 0xffff) << 12);

    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;
    cout << "result2 = 0x" << result2.ui64[0] << endl;
    cout << "result3 = 0x" << result3.ui64[0] << endl;

}
```

```Output
result1 = 0xfffffffff3210fff
result2 = 0xfffffffff3210fff
result3 = 0xfffffffff3210fff
```

**Microsoft 固有の仕様はここまで**

高度なマイクロ デバイス, inc. copyright 2007All rights reserved. 高度なマイクロ デバイス, Inc. からのアクセス許可を持つ再現

## <a name="see-also"></a>関連項目

[_mm_extract_si64、_mm_extracti_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)