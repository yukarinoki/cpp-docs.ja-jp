---
title: _mm_extract_si64、_mm_extracti_si64
ms.date: 11/04/2016
f1_keywords:
- _mm_extracti_si64
- _mm_extract_si64
helpviewer_keywords:
- extrq instruction
- _mm_extracti_si64 intrinsic
- _mm_extract_si64 intrinsic
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
ms.openlocfilehash: e77ca5589ed50a4199921603afec1d9888c6cca5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040213"
---
# <a name="mmextractsi64-mmextractisi64"></a>_mm_extract_si64、_mm_extracti_si64

**Microsoft 固有の仕様**

生成、`extrq`最初の引数の下位 64 ビットから指定のビットを抽出する命令です。

## <a name="syntax"></a>構文

```
__m128i _mm_extract_si64(
   __m128i Source,
   __m128i Descriptor
);
__m128i _mm_extracti_si64(
   __m128i Source,
   int Length,
   int Index
);
```

#### <a name="parameters"></a>パラメーター

*ソース*<br/>
[in]下位 64 ビットの入力データでは、128 ビット フィールドです。

*記述子*<br/>
[in]抽出するビット フィールドを表す 128 ビット フィールドです。

*長さ*<br/>
[in]抽出するフィールドの長さを指定する整数。

*Index*<br/>
[in]抽出するフィールドのインデックスを指定する整数

## <a name="return-value"></a>戻り値

抽出された、最下位ビット フィールドは、128 ビット フィールドです。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`_mm_extract_si64`|SSE4a|
|`_mm_extracti_si64`|SSE4a|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

この組み込みを生成、`extrq`からビットを抽出する命令`Source`します。この 2 つのバージョンがある組み込み:`_mm_extracti_si64`即時のバージョンと`_mm_extract_si64`緊急であります。  各バージョンの抽出から`Source`その長さと、その最下位ビットのインデックスで定義されたビット フィールド。 Mod 64 を長さとインデックスの値が表示されます、-1 から 127 文字の両方が 63 として解釈されます。 (縮小) のインデックスと (縮小) フィールドの長さの合計が 64 よりも大きい場合は、結果は定義されていません。 フィールド長に 0 の値は、64 として解釈されます。 場合、フィールドの長さとビットのインデックスの両方で 0 ビット 63:0`Source`抽出されます。 フィールドの長さが 0 ビットのインデックスが 0 でない場合、結果は定義されていません。

_Mm_extract_si64 への呼び出しで、`Descriptor`ビット 13:8 ビット 5:0 で抽出するデータのフィールドの長さでインデックスが含まれています.

呼び出す場合`_mm_extracti_si64`、コンパイラをコンパイラは、整数定数である判断できない引数を持つには、これらの値を XMM レジスタにパックするコードを生成します (`Descriptor`) を呼び出すと`_mm_extract_si64`します。

ハードウェア サポートの決定を`extrq`命令、呼び出し、`__cpuid`で組み込み`InfoType=0x80000001`のビット 6 をチェックし、`CPUInfo[2] (ECX)`します。 このビットは、それ以外の場合、命令がサポートされている場合は 1、0 になります。 この組み込みのハードウェアがサポートされていないを使用するコードを実行するかどうか、`extrq`命令の場合、結果は予測できません。

## <a name="example"></a>例

```
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

union {
    __m128i m;
    unsigned __int64 ui64[2];
} source, descriptor, result1, result2, result3;

int
main()
{
    source.ui64[0] =     0xfedcba9876543210ll;
    descriptor.ui64[0] = 0x0000000000000b1bll;

    result1.m = _mm_extract_si64 (source.m, descriptor.m);
    result2.m = _mm_extracti_si64(source.m, 27, 11);
    result3.ui64[0] = (source.ui64[0] >> 11) & 0x7ffffff;

    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;
    cout << "result2 = 0x" << result2.ui64[0] << endl;
    cout << "result3 = 0x" << result3.ui64[0] << endl;
}
```

```Output
result1 = 0x30eca86
result2 = 0x30eca86
result3 = 0x30eca86
```

**Microsoft 固有の仕様はここまで**

高度なマイクロ デバイス, inc. copyright 2007All rights reserved. 高度なマイクロ デバイス, Inc. からのアクセス許可を持つ再現

## <a name="see-also"></a>関連項目

[_mm_insert_si64、_mm_inserti_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)