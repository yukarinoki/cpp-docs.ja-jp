---
description: '詳細については、次を参照してください: _mm_stream_ss'
title: _mm_stream_ss
ms.date: 09/02/2019
f1_keywords:
- _mm_stream_ss
helpviewer_keywords:
- movntss instruction
- _mm_stream_ss intrinsic
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
ms.openlocfilehash: 3af79ee38c09f08ab8e1e5300800846c866972a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133208"
---
# <a name="_mm_stream_ss"></a>_mm_stream_ss

**Microsoft 固有の仕様**

キャッシュを汚染せずに、32ビットのデータをメモリ位置に書き込みます。

## <a name="syntax"></a>構文

```C
void _mm_stream_ss(
   float * Destination,
   __m128 Source
);
```

### <a name="parameters"></a>パラメーター

*インストール*\
入出力ソースデータが書き込まれる場所へのポインター。

*電源*\
から **`float`** 下位32ビットに書き込まれる値を含む128ビットの数値。

## <a name="return-value"></a>戻り値

[なし] :

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`_mm_stream_ss`|SSE4a|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

組み込みによって命令が生成され `movntss` ます。 この命令のハードウェアサポートを確認するには、で組み込みのを呼び出し、 `__cpuid` `InfoType=0x80000001` のビット6を確認し `CPUInfo[2] (ECX)` ます。 命令がサポートされている場合はこのビットが1になり、それ以外の場合は0になります。

命令をサポートしていないハードウェアに組み込みを使用するコードを実行する場合、 `_mm_stream_ss` `movntss` 結果は予測できません。

## <a name="example"></a>例

```cpp
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
    __m128 vals;
    float f[4];

    f[0] = -1.;
    f[1] = -2.;
    f[2] = -3.;
    f[3] = -4.;
    vals.m128_f32[0] = 0.;
    vals.m128_f32[1] = 1.;
    vals.m128_f32[2] = 2.;
    vals.m128_f32[3] = 3.;
    _mm_stream_ss(&f[3], vals);
    cout << "f[0] = " << f[0] << ", f[1] = " << f[1] << endl;
    cout << "f[1] = " << f[1] << ", f[3] = " << f[3] << endl;
}
```

```Output
f[0] = -1, f[1] = -2
f[2] = -3, f[3] = 3
```

**Microsoft 固有の仕様はここまで**

高度なマイクロデバイス (Inc.) による部分の著作権2007すべての権限が予約されています。 上級マイクロデバイス (Inc.) からのアクセス許可を使用して再現されます。

## <a name="see-also"></a>関連項目

[_mm_stream_sd](../intrinsics/mm-stream-sd.md)\
[_mm_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_ps)\
[_mm_store_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ss)\
[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
