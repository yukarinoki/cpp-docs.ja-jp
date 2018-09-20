---
title: _mm_stream_sd |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_stream_sd
dev_langs:
- C++
helpviewer_keywords:
- _mm_stream_sd intrinsic
- movntsd instruction
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b965c1882e6126f34e9e81c99c950e072246db97
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437606"
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

*Source*<br/>
[in]128 ビット値を含む、 `double` 64 ビットの下には書き込まれる値.

## <a name="return-value"></a>戻り値

なし。

## <a name="requirements"></a>要件

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