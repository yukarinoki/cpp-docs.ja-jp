---
title: difftime、_difftime32、_difftime64
ms.date: 11/04/2016
apiname:
- _difftime32
- difftime
- _difftime64
apilocation:
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _difftime64
- difftime
- difftime64
- _difftime32
- difftime32
helpviewer_keywords:
- _difftime32 function
- difftime function
- time, finding the difference
- difftime64 function
- _difftime64 function
- difftime32 function
ms.assetid: 4cc0ac2b-fc7b-42c0-8283-8c9d10c566d0
ms.openlocfilehash: eefa946f0458f79950b443c0a84272866845df8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505951"
---
# <a name="difftime-difftime32-difftime64"></a>difftime、_difftime32、_difftime64

2 つの時刻の差を取得します。

## <a name="syntax"></a>構文

```C
double difftime( time_t timeEnd, time_t timeStart );
double _difftime32( __time32_t timeEnd, __time32_t timeStart );
double _difftime64( __time64_t timeEnd, __time64_t timeStart );
```

### <a name="parameters"></a>パラメーター

*時刻終了*<br/>
終了時刻。

*TimeStart*<br/>
開始時刻。

## <a name="return-value"></a>戻り値

**difftime** (秒単位) からの経過時間を返します*timeStart*に*時刻終了*します。 返される値は、倍精度浮動小数点数です。 戻り値が 0 の場合は、エラーを示します。

## <a name="remarks"></a>Remarks

**Difftime**関数は、2 つの指定された時間値の差を計算*timeStart*と*時刻終了*します。

時刻の値を指定する必要がありますの範囲内に収まる**time_t**します。 **time_t**は 64 ビット値です。 したがって、範囲の終わりは、2038 年 1 月 18 日 23 時 59 分 59 秒 (UTC) から、3000 年 12 月 31 日 23 時 59 分 59 秒に拡張されました。 範囲の**time_t** 1970 年 1 月 1 日午前 0 時が。

**difftime**いずれかに評価されるインライン関数は、 **_difftime32**または **_difftime64**かどうかに応じて **_USE_32BIT_TIME_T**が定義されています。 _difftime32 と _difftime64 を直接使って、特定のサイズの時刻型の使用を強制できます。

これらの関数では、パラメーターの検証が行われます。 どちらかのパラメーターが 0 または負の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効パラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は 0 を返します設定と**errno**に**EINVAL**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**difftime**|\<time.h>|
|**_difftime32**|\<time.h>|
|**_difftime64**|\<time.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```cpp
// crt_difftime.c
// This program calculates the amount of time
// needed to do a floating-point multiply 100 million times.
//

#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <float.h>

double RangedRand( float range_min, float range_max)
{
   // Generate random numbers in the half-closed interval
   // [range_min, range_max). In other words,
   // range_min <= random number < range_max
   return ((double)rand() / (RAND_MAX + 1) * (range_max - range_min)
            + range_min);
}

int main( void )
{
   time_t   start, finish;
   long     loop;
   double   result, elapsed_time;
   double   arNums[3];

   // Seed the random-number generator with the current time so that
   // the numbers will be different every time we run.
   srand( (unsigned)time( NULL ) );

   arNums[0] = RangedRand(1, FLT_MAX);
   arNums[1] = RangedRand(1, FLT_MAX);
   arNums[2] = RangedRand(1, FLT_MAX);
   printf( "Using floating point numbers %.5e %.5e %.5e\n", arNums[0], arNums[1], arNums[2] );

   printf( "Multiplying 2 numbers 100 million times...\n" );

   time( &start );
   for( loop = 0; loop < 100000000; loop++ )
      result = arNums[loop%3] * arNums[(loop+1)%3];
   time( &finish );

   elapsed_time = difftime( finish, start );
   printf( "\nProgram takes %6.0f seconds.\n", elapsed_time );
}

```

```Output
Using random floating point numbers 1.04749e+038 2.01482e+038 1.72737e+038Multiplying 2 floating point numbers 100 million times...Program takes      3 seconds.Multiplying 2 floating point numbers 500 million times...

Program takes      5 seconds.
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[時間管理](../../c-runtime-library/time-management.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
