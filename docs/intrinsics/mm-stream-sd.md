---
title: _mm_stream_sd
ms.date: 11/04/2016
f1_keywords:
- _mm_stream_sd
helpviewer_keywords:
- _mm_stream_sd intrinsic
- movntsd instruction
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
ms.openlocfilehash: 3555b71e15d6f9c618a83f573d6da3cda9e7b705
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263244"
---
# <a name="mmstreamsd"></a>_mm_stream_sd

**Microsoft 固有の仕様**

キャッシュの汚染せずメモリ位置を 64 ビットのデータを書き込みます。

## <a name="syntax"></a>構文

```
void _mm_stream_sd(
   double * Dest,
   __m128d Source
);
```

#### <a name="parameters"></a>パラメーター

*追加先*<br/>
[out]ソース データの書き込み先の場所へのポインター。

*ソース*<br/>
[in]128 ビット値を含む、 `double` 64 ビットの下には書き込まれる値.

## <a name="return-value"></a>戻り値

なし。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`_mm_stream_sd`|SSE4a|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>コメント

この組み込み関数は`movntsd`命令を生成します。 この命令のハードウェアのサポートを確認するのには、呼び出し、`__cpuid`で組み込み`InfoType=0x80000001`のビット 6 をチェックおよび`CPUInfo[2] (ECX)`します。 ハードウェアがサポートする場合、この命令と 0 それ以外の場合、このビットは 1 です。

使用するコードを実行する場合、`_mm_stream_sd`がサポートされていないハードウェアに組み込み、`movntsd`命令の場合、結果は予測できません。

## <a name="example"></a>例

```
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
    __m128d vals;
    double d[2];

    d[0] = -1.;
    d[1] = -2.;
    vals.m128d_f64[0] = 0.;
    vals.m128d_f64[1] = 1.;
    _mm_stream_sd(&d[1], vals);
    cout << "d[0] = " << d[0] << ", d[1] = " << d[1] << endl;
}
```

```Output
d[0] = -1, d[1] = 1
```

**Microsoft 固有の仕様はここまで**

高度なマイクロ デバイス, inc. copyright 2007All rights reserved. 高度なマイクロ デバイス, Inc. からのアクセス許可を持つ再現

## <a name="see-also"></a>関連項目

[_mm_stream_ss](../intrinsics/mm-stream-ss.md)<br/>
[_mm_store_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_sd)<br/>
[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)