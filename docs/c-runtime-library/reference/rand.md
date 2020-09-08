---
title: rand
description: よく知られている、完全に再現可能なアルゴリズムを使用して擬似乱数を生成する rand の API リファレンス。
ms.date: 4/2/2020
api_name:
- rand
- _o_rand
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- rand
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, generating
- numbers, pseudorandom
- rand function
- pseudorandom numbers
- numbers, generating pseudorandom
ms.openlocfilehash: 50c4f921c81ecad00abb19e6ce50158d450b170e
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555333"
---
# <a name="rand"></a>rand

よく知られている、完全に再現可能なアルゴリズムを使用して、擬似乱数を生成します。 プログラムによってセキュリティで保護されたこの関数のバージョンを利用できます。「 [rand_s](rand-s.md)」を参照してください。 **Rand**によって生成される数値は、暗号的には安全ではありません。 より暗号的に安全な乱数生成を行うには、 [rand_s](rand-s.md) またはの C++ 標準ライブラリで宣言されている関数を使用し [\<random>](../../standard-library/random.md) ます。

## <a name="syntax"></a>構文

```C
int rand( void );
```

## <a name="return-value"></a>戻り値

前に説明したように、 **rand**は擬似乱数を返します。 エラーの戻り値はありません。

## <a name="remarks"></a>解説

**Rand**関数は、0 ~ **RAND_MAX** (32767) の範囲で、擬似乱数の整数を返します。 [Srand](srand.md)関数を使用して、 **rand**を呼び出す前に擬似乱数ジェネレーターをシード処理します。

**Rand**関数は、既知のシーケンスを生成します。暗号関数としての使用には適していません。 より暗号的に安全な乱数生成を行うには、 [rand_s](rand-s.md) またはの C++ 標準ライブラリで宣言されている関数を使用し [\<random>](../../standard-library/random.md) ます。 **Rand**の問題と、これらの欠点に対処する方法について \<random> は、「互換性の[ある rand と見なさ](https://channel9.msdn.com/Events/GoingNative/2013/rand-Considered-Harmful)れるこのビデオ」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**rand**|\<stdlib.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_rand.c
// This program seeds the random-number generator
// with the time, then exercises the rand function.
//

#include <stdlib.h>
#include <stdio.h>
#include <time.h>

void SimpleRandDemo( int n )
{
   // Print n random numbers.
   int i;
   for( i = 0; i < n; i++ )
      printf( "  %6d\n", rand() );
}

void RangedRandDemo( int range_min, int range_max, int n )
{
   // Generate random numbers in the half-closed interval
   // [range_min, range_max). In other words,
   // range_min <= random number < range_max
   int i;
   for ( i = 0; i < n; i++ )
   {
      int u = (double)rand() / (RAND_MAX + 1) * (range_max - range_min)
            + range_min;
      printf( "  %6d\n", u);
   }
}

int main( void )
{
   // Seed the random-number generator with the current time so that
   // the numbers will be different every time we run.
   srand( (unsigned)time( NULL ) );

   SimpleRandDemo( 10 );
   printf("\n");
   RangedRandDemo( -100, 100, 10 );
}
```

```Output
22036
18330
11651
27464
18093
3284
11785
14686
11447
11285

   74
   48
   27
   65
   96
   64
   -5
  -42
  -55
   66
```

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[srand](srand.md)<br/>
[rand_s](rand-s.md)<br/>
