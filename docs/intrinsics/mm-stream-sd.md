---
description: '詳細については、次を参照してください: _mm_stream_sd'
title: _mm_stream_sd
ms.date: 09/02/2019
f1_keywords:
- _mm_stream_sd
helpviewer_keywords:
- _mm_stream_sd intrinsic
- movntsd instruction
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
ms.openlocfilehash: 60ef13afcbe99e1390f4eb1087fddc5540a7de34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133264"
---
# <a name="_mm_stream_sd"></a>_mm_stream_sd

**Microsoft 固有の仕様**

キャッシュを汚染せずに、64ビットのデータをメモリ位置に書き込みます。

## <a name="syntax"></a>構文

```C
void _mm_stream_sd(
   double * Dest,
   __m128d Source
);
```

### <a name="parameters"></a>パラメーター

*先*\
入出力ソースデータが書き込まれる場所へのポインター。

*電源*\
から **`double`** 下位64ビットで記述される値を格納している128ビット値。

## <a name="return-value"></a>戻り値

[なし] :

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`_mm_stream_sd`|SSE4a|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

組み込みによって命令が生成され `movntsd` ます。 この命令のハードウェアサポートを確認するには、で組み込みのを呼び出し、 `__cpuid` `InfoType=0x80000001` のビット6を確認し `CPUInfo[2] (ECX)` ます。 ハードウェアでこの命令がサポートされている場合、このビットは1になり、それ以外の場合は0になります。

命令をサポートしていないハードウェアに組み込みを使用するコードを実行する場合、 `_mm_stream_sd` `movntsd` 結果は予測できません。

## <a name="example"></a>例

```cpp
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

高度なマイクロデバイス (Inc.) による部分の著作権2007すべての権限が予約されています。 上級マイクロデバイス (Inc.) からのアクセス許可を使用して再現されます。

## <a name="see-also"></a>関連項目

[_mm_stream_ss](../intrinsics/mm-stream-ss.md)\
[_mm_store_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_sd)\
[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
