---
title: clock
ms.date: 11/04/2016
apiname:
- clock
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
- clock
helpviewer_keywords:
- processor time used, calculating
- time, calculating processor
- clock function
- processor time used
- calculating processor time used
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
ms.openlocfilehash: 4b58b33b533250447cf964134de9869bddee4498
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492640"
---
# <a name="clock"></a>clock

呼び出しプロセスにかかったウォール クロック時間を計算します。

## <a name="syntax"></a>構文

```C
clock_t clock( void );
```

## <a name="return-value"></a>戻り値

プロセスの開始時の CRT の初期化からの経過時間の単位で**CLOCKS_PER_SEC** 1 秒あたりのユニットです。 経過時間が利用できないかとして記録できる正の最大期間を超えた場合、 **clock_t**型、関数が値を返します`(clock_t)(-1)`します。

## <a name="remarks"></a>Remarks

**クロック**CRT の初期化プロセス開始時から経過したウォール クロック時間が関数に指示します。 この関数は、厳密には ISO C (正味の CPU 時間を戻り値にすることが規定されている) に準拠していないことに注意してください。 CPU 時間を取得するには、Win32 の [GetProcessTimes](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getprocesstimes) 関数を使用します。 経過時間 (秒) を確認するのにによって返される値で除算、**クロック**マクロによって関数**CLOCKS_PER_SEC**します。

十分な時間を指定するには、によって返される値**クロック**の正の最大値を超える**clock_t**します。 ときに、プロセスが実行時間が長い、によって返される値**クロック**は常に`(clock_t)(-1)`ISO C99 標準 (7.23.2.1) と ISO C11 標準 (7.27.2.1) で指定されたとおりです。 Microsoft の実装**clock_t**として、**長い**、符号付き 32 ビット整数では、および**CLOCKS_PER_SEC**マクロは 1000 として定義されます。 これにより、最大**クロック**関数の戻り値は 2147483.647 秒、または約 24.8 日。 によって返される値に依存しない**クロック**でこの時間より長く実行されるプロセス。 64 ビットを使用する[時間](time-time32-time64.md)関数または、Windows [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904)関数を何年ものレコードの処理の経過時間。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**clock**|\<time.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_clock.c
// This sample uses clock() to 'sleep' for three
// seconds, then determines how long it takes
// to execute an empty loop 600000000 times.

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

// Pauses for a specified number of milliseconds.
void do_sleep( clock_t wait )
{
   clock_t goal;
   goal = wait + clock();
   while( goal > clock() )
      ;
}

const long num_loops = 600000000L;

int main( void )
{
   long    i = num_loops;
   clock_t start, finish;
   double  duration;

   // Delay for a specified time.
   printf( "Delay for three seconds\n" );
   do_sleep( (clock_t)3 * CLOCKS_PER_SEC );
   printf( "Done!\n" );

   // Measure the duration of an event.
   start = clock();
   while( i-- )
      ;
   finish = clock();
   duration = (double)(finish - start) / CLOCKS_PER_SEC;
   printf( "Time to do %ld empty loops is ", num_loops );
   printf( "%2.3f seconds\n", duration );
}
```

```Output
Delay for three seconds
Done!
Time to do 600000000 empty loops is 1.354 seconds
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[difftime、_difftime32、_difftime64](difftime-difftime32-difftime64.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
