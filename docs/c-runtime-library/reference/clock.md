---
title: clock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- processor time used, calculating
- time, calculating processor
- clock function
- processor time used
- calculating processor time used
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4caf2518de21a938822e443c0383c22cf170d44
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395368"
---
# <a name="clock"></a>clock

呼び出しプロセスにかかったウォール クロック時間を計算します。

## <a name="syntax"></a>構文

```C
clock_t clock( void );
```

## <a name="return-value"></a>戻り値

CRT の初期化をプロセスの開始時からの経過時間の単位で**CLOCKS_PER_SEC** 1 秒あたりの単位。 経過時間が使用できないかとして記録できる最大の正の時間を超えた場合、 **clock_t**型、値を返します、`(clock_t)(-1)`です。

## <a name="remarks"></a>コメント

**クロック**関数は CRT の初期化プロセスの開始時以降にかかったウォール クロック時間が経過を通知します。 この関数は、厳密には ISO C (正味の CPU 時間を戻り値にすることが規定されている) に準拠していないことに注意してください。 CPU 時間を取得するには、Win32 の [GetProcessTimes](https://msdn.microsoft.com/library/windows/desktop/ms683223) 関数を使用します。 によって返される値で除算を秒単位の経過時間を確認するのには**クロック**マクロによって関数**CLOCKS_PER_SEC**です。

十分な時間を指定するには、によって返される値**クロック**の最大の正の値を超えることができます**clock_t**です。 ときに、プロセスが長い時間実行、によって返される値**クロック**は常に`(clock_t)(-1)`ISO C99 標準 (7.23.2.1) と ISO C11 標準 (7.27.2.1) で指定されたとおりです。 Microsoft が実装する**clock_t**として、**長い**、符号付き 32 ビット整数では、および**CLOCKS_PER_SEC**を 1000 マクロが定義されています。 こうと、最大**クロック**関数の戻り値は 2147483.647 秒、または約 24.8 日。 によって返される値に依存しない**クロック**時間より長い実行プロセスでします。 64 ビットを使用することができます[時間](time-time32-time64.md)関数または Windows [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904)何年ものレコードの処理の経過時間をする関数。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
