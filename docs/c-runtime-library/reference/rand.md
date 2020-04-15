---
title: rand
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 944c512d0102b459afc2924ef7515311e46cd43c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338157"
---
# <a name="rand"></a>rand

既知の完全再現性のあるアルゴリズムを使用して、擬似乱数を生成します。 この関数のプログラムでセキュリティ保護されたバージョンを使用できます。[rand_s](rand-s.md)を参照してください。 **ランド**によって生成された番号は、暗号的に安全ではありません。 より暗号化された安全な乱数生成を行う場合は[、rand_s](rand-s.md)または C++ 標準ライブラリで宣言された関数を[\<ランダム>](../../standard-library/random.md)で使用します。

## <a name="syntax"></a>構文

```C
int rand( void );
```

## <a name="return-value"></a>戻り値

**rand は**、上記のように擬似乱数を返します。 エラーの戻り値はありません。

## <a name="remarks"></a>解説

**rand**関数は、0 から**RAND_MAX** (32767) の範囲の擬似乱数整数を返します。 [srand](srand.md)関数を使用して、rand**を呼び**出す前に擬似乱数ジェネレータをシードします。

**rand**関数は、既知のシーケンスを生成し、暗号関数として使用するのに適していません。 より暗号化された安全な乱数生成を行う場合は[、rand_s](rand-s.md)または C++ 標準ライブラリで宣言された関数を[\<ランダム>](../../standard-library/random.md)で使用します。 **ランド**の何が悪いのか、そしてランダムな>がこれらの\<欠点にどのように対処するかについての詳細については、このビデオ[「rand有害とみなされる](https://channel9.msdn.com/Events/GoingNative/2013/rand-Considered-Harmful)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
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

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[srand](srand.md)<br/>
[rand_s](rand-s.md)<br/>
