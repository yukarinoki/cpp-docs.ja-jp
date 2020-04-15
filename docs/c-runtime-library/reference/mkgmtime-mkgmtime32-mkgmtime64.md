---
title: _mkgmtime、_mkgmtime32、_mkgmtime64
description: C ランタイム ライブラリの_mkgmtime、_mkgmtime32、および_mkgmtime64関数について説明し、その使用方法の例を示します。
ms.date: 4/2/2020
api_name:
- _mkgmtime32
- _mkgmtime64
- _mkgmtime
- _o__mkgmtime32
- _o__mkgmtime64
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
- _mkgmtime64
- mkgmtime32
- _mkgmtime32
- mkgmtime
- mkgmtime64
- _mkgmtime
helpviewer_keywords:
- mkgmtime32 function
- time functions
- mkgmtime function
- _mkgmtime function
- converting times
- mkgmtime64 function
- _mkgmtime64 function
- _mkgmtime32 function
- time, converting
ms.assetid: b4ca2b67-e198-4f43-b3e2-e8ad6bd01867
ms.openlocfilehash: e8b3170fc0413a878777035fd76aac5eefa7b6bf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338769"
---
# <a name="_mkgmtime-_mkgmtime32-_mkgmtime64"></a>_mkgmtime、_mkgmtime32、_mkgmtime64

**構造体** **tm**で表される UTC 時刻を **、time_t**型で表される UTC 時刻に変換します。

## <a name="syntax"></a>構文

```C
time_t _mkgmtime(
   struct tm* timeptr
);
__time32_t _mkgmtime32(
   struct tm* timeptr
);
__time64_t _mkgmtime64(
   struct tm* timeptr
);
```

### <a name="parameters"></a>パラメーター

*タイムプター*\
変換する**構造体** **tm**としての UTC 時刻へのポインター。

## <a name="return-value"></a>戻り値

1970 年 1 月 1 日午前 0 時から経過した秒数を表す **__time32_t**または **__time64_t**の数量 (UTC)。 日付が範囲外の場合 (「解説」セクションを参照)、または入力を有効な時刻として解釈できない場合、戻り値は -1 です。

## <a name="remarks"></a>解説

**_mkgmtime32**関数と **_mkgmtime64**関数は、UTC 時刻を **__time32_t**または **__time64_t**の型に変換します。 現地時刻を UTC 時刻に変換するには **、mktime**、 **_mktime32、** および **_mktime64**を代わりに使用します。

**_mkgmtime**はインライン関数で **、 _mkgmtime64**と評価され **、time_t**は **__time64_t**と同等です。 コンパイラが古い 32 ビット**time_t**として**time_t**を解釈するようにする必要がある場合は、 **_USE_32BIT_TIME_T**を定義できます。 2038 年 1 月 18 日以降、アプリケーションが失敗する可能性があるため、32 ビット**time_t**の最大範囲を使用することはお勧めしません。 64 ビット プラットフォームでは、まったく許可されていません。

渡された時間構造は **、_mktime**関数によって変更されるのと同じ方法で、次のように変更されます: **tm_wday**と**tm_yday**フィールドは **、tm_mday**と**tm_year**の値に基づいて新しい値に設定されます。 時刻は UTC と見なされるため **、tm_isdst**フィールドは無視されます。

**_mkgmtime32**関数の範囲は、1970 年 1 月 1 日午前 0 時から UTC 23:59:59、2038年 1 月 18 日までです。 **_mkgmtime64**の範囲は、1970 年 1 月 1 日午前 0 時から UTC の 23:59:59、3000、12 月 31 日、UTC です。 範囲外の日付は、-1 の戻り値になります。 **_mkgmtime**の範囲は **、_USE_32BIT_TIME_T**が定義されているかどうかによって異なります。 定義されていない場合 (既定値)、範囲は **_mkgmtime64**と同じになります。 それ以外の場合、範囲は _mkgmtime32 の 32 ビット範囲に制限**されます**。

**gmtime**と**ローカル時間**の両方が、変換に共通の静的バッファーを使用します。 このバッファーを **_mkgmtime**に指定すると、以前の内容は破棄されます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="examples"></a>例

```C
// crt_mkgmtime.c
#include <stdio.h>
#include <time.h>

int main()
{
    struct tm t1, t2;
    time_t now, mytime, gmtime;
    char buff[30];

    time( & now );

    _localtime64_s( &t1, &now );
    _gmtime64_s( &t2, &now );

    mytime = mktime(&t1);
    gmtime = _mkgmtime(&t2);

    printf("Seconds since midnight, January 1, 1970\n");
    printf("My time: %I64d\nGM time (UTC): %I64d\n\n", mytime, gmtime);

    /* Use asctime_s to display these times. */

    _localtime64_s( &t1, &mytime );
    asctime_s( buff, sizeof(buff), &t1 );
    printf( "Local Time: %s\n", buff );

    _gmtime64_s( &t2, &gmtime );
    asctime_s( buff, sizeof(buff), &t2 );
    printf( "Greenwich Mean Time: %s\n", buff );

}
```

```Output
Seconds since midnight, January 1, 1970
My time: 1171588492
GM time (UTC): 1171588492

Local Time: Thu Feb 15 17:14:52 2007

Greenwich Mean Time: Fri Feb 16 01:14:52 2007
```

次の例は、不完全な構造体が **_mkgmtime**によってどのように入力されているかを示しています。 曜日と年の両方の値を計算します。

```C
// crt_mkgmtime2.c
#include <stdio.h>
#include <time.h>
#include <memory.h>

int main()
{
    struct tm t1, t2;
    time_t gmtime;
    char buff[30];

    memset(&t1, 0, sizeof(struct tm));
    memset(&t2, 0, sizeof(struct tm));

    t1.tm_mon = 1;
    t1.tm_isdst = 0;
    t1.tm_year = 103;
    t1.tm_mday = 12;

    // The day of the week and year will be incorrect in the output here.
    asctime_s( buff, sizeof(buff), &t1);
    printf("Before calling _mkgmtime, t1 = %s t.tm_yday = %d\n",
            buff, t1.tm_yday );

    gmtime = _mkgmtime(&t1);

    // The correct day of the week and year were determined.
    asctime_s( buff, sizeof(buff), &t1);
    printf("After calling _mkgmtime, t1 = %s t.tm_yday = %d\n",
            buff, t1.tm_yday );

}
```

```Output
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003
t.tm_yday = 0
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003
t.tm_yday = 42
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)\
[アスクタイム,_wasctime](asctime-wasctime.md)\
[asctime_s、_wasctime_s](asctime-s-wasctime-s.md)\
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)\
[gmtime_s、_gmtime32_s、_gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)\
[localtime_s、_localtime32_s、_localtime64_s](localtime-s-localtime32-s-localtime64-s.md)\
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)\
[time、_time32、_time64](time-time32-time64.md)
