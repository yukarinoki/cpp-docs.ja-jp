---
title: _mkgmtime、_mkgmtime32、_mkgmtime64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mkgmtime32
- _mkgmtime64
- _mkgmtime
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
- _mkgmtime64
- mkgmtime32
- _mkgmtime32
- mkgmtime
- mkgmtime64
- _mkgmtime
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcb587cf5504f661512ccf88cf4f15d0555e2f18
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="mkgmtime-mkgmtime32-mkgmtime64"></a>_mkgmtime、_mkgmtime32、_mkgmtime64

によって表される UTC 時刻に変換、**構造体** **tm**を UTC 時刻で表される、 **time_t**型です。

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

*timeptr*<br/>
UTC 時刻としてへのポインター、**構造体** **tm**に変換します。

## <a name="return-value"></a>戻り値

型の数量 **_time32_t**または **_ _time64_t**世界協定時刻 (UTC) で 1970 年 1 月 1 日午前 0 時から経過した秒数を表すです。 日付が範囲外の場合 (「解説」セクションを参照してください) または入力、有効な時刻として解釈できない場合、戻り値は-1。

## <a name="remarks"></a>コメント

**_Mkgmtime32**と **_mkgmtime64**関数に変換すると、UTC 時間、 **_time32_t**または **_ _time64_t**で時刻を表す型UTC です。 ローカル時刻を UTC 時刻に変換するには使用**mktime**、 **_mktime32**、および **_mktime64**代わりにします。

**_mkgmtime**に評価されるインライン関数は、 **_mkgmtime64**、および**time_t**は等価 **_ _time64_t**です。 強制的に、コンパイラを解釈する必要がある場合**time_t**古い 32 ビットとして**time_t**を定義できます **_USE_32BIT_TIME_T**です。 これは推奨されません、アプリケーションは、2038 年 1 月 18 日後に失敗する可能性があります (32 ビットの最大範囲**time_t**)、64 ビット プラットフォームではまったく許可されていないとします。

構造体が渡される次のように内に変更されますと同じ方法で変更されるたび、**体**関数: **tm_wday**と**tm_yday**フィールドに新しい設定するには値の値に基づいて**tm_mday**と**tm_year**です。 指定する場合、 **tm**時間構造体は、設定、 **tm_isdst**フィールドを。

- 標準時間が有効であることを示す場合はゼロ (0)。

- 夏時間が有効であることを示す場合は 0 より大きい値。

- 標準時間と夏時間のどちらが有効であるかを C ランタイム ライブラリ コードで計算する場合は 0 より小さい値。

C ランタイム ライブラリは、TZ 環境変数を使用して、正しい夏時間を特定します。 TZ が設定されていない場合は、オペレーティング システムに照会して、正しい地域の夏時間の動作を取得します。 **tm_isdst**フィールドは必須です。 かどうか設定されていない、その値は未定義とからの戻り値**mktime**は予測できません。

範囲、 **_mkgmtime32**関数は午前 0 時、1970 年 1 月 1 日から 23時 59分: 59 2038 年 1 月 18 日 (utc) に UTC です。 範囲 **_mkgmtime64** 3000 年 12 月 31 日 23時 59分: 59 秒 UTC 午前 0 時、1970 年 1 月 1 日 (utc) からです。 範囲外の日付は、戻り値-1 になります。 範囲 **_mkgmtime**かどうかによって異なります **_USE_32BIT_TIME_T**が定義されています。 (既定) が定義されていない場合、範囲は **_mkgmtime64**、それ以外の範囲は、の 32 ビットの範囲に制限されて **_mkgmtime32**です。

なお**gmtime**と**localtime**変換に 1 つの静的に割り当てられたバッファーを使用します。 このバッファーを指定する場合**mkgmtime**、以前の内容は破棄されます。

## <a name="example"></a>例

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

### <a name="sample-output"></a>出力例

```Output
Seconds since midnight, January 1, 1970
My time: 1171588492
GM time (UTC): 1171588492

Local Time: Thu Feb 15 17:14:52 2007

Greenwich Mean Time: Fri Feb 16 01:14:52 2007
```

未完成の構造体に曜日と年通算日の計算値を入力する例を次に示します。

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

### <a name="output"></a>出力

```Output
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003
t.tm_yday = 0
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003
t.tm_yday = 42
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime、_wasctime](asctime-wasctime.md)<br/>
[asctime_s、_wasctime_s](asctime-s-wasctime-s.md)<br/>
[gmtime、_gmtime32、_gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[gmtime_s、_gmtime32_s、_gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s、_localtime32_s、_localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime、_mktime32、_mktime64](mktime-mktime32-mktime64.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
