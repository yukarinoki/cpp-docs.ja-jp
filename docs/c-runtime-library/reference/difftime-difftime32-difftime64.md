---
title: difftime、_difftime32、_difftime64
ms.date: 4/2/2020
api_name:
- _difftime32
- difftime
- _difftime64
- _o__difftime32
- _o__difftime64
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: e2573f0bd5120796c0185c4dafe2699f8ceaae29
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348132"
---
# <a name="difftime-_difftime32-_difftime64"></a>difftime、_difftime32、_difftime64

2 つの時刻の差を取得します。

## <a name="syntax"></a>構文

```C
double difftime( time_t timeEnd, time_t timeStart );
double _difftime32( __time32_t timeEnd, __time32_t timeStart );
double _difftime64( __time64_t timeEnd, __time64_t timeStart );
```

### <a name="parameters"></a>パラメーター

*タイムエンド*<br/>
終了時刻。

*タイムスタート*<br/>
開始時刻。

## <a name="return-value"></a>戻り値

**difftime**は、timeStart から*timeEnd*までの経過時間を秒単位*で返します*。 返される値は、倍精度浮動小数点数です。 戻り値が 0 の場合は、エラーを示します。

## <a name="remarks"></a>解説

**difftime**関数は、指定された 2 つの時刻値*timeStart*と*timeEnd*の差を計算します。

指定する時間の値は **、time_t**の範囲内に収まる必要があります。 **time_t**は 64 ビット値です。 したがって、範囲の終わりは、2038 年 1 月 18 日 23 時 59 分 59 秒 (UTC) から、3000 年 12 月 31 日 23 時 59 分 59 秒に拡張されました。 **time_t**の下限は1970年1月1日の午前0時です。

**difftime**は、_USE_32BIT_TIME_Tが**定義されているかどうかによって****_difftime32**または **_difftime64**に評価されるインライン関数です。 _difftime32 と _difftime64 を直接使って、特定のサイズの時刻型の使用を強制できます。

これらの関数では、パラメーターの検証が行われます。 どちらかのパラメーターが 0 または負の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効パラメーター ハンドラーが呼び出されます。 実行を続行できる場合、これらの関数は 0 を返し **、errno**を**EINVAL**に設定します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**difftime**|\<time.h>|
|**_difftime32**|\<time.h>|
|**_difftime64**|\<time.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
Using random floating point numbers 1.04749e+038 2.01482e+038 1.72737e+038
Multiplying 2 floating point numbers 100 million times...
Program takes      3 seconds.
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[時間管理](../../c-runtime-library/time-management.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
