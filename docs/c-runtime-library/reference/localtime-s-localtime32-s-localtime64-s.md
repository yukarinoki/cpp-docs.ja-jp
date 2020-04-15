---
title: localtime_s、_localtime32_s、_localtime64_s
ms.date: 4/2/2020
api_name:
- _localtime64_s
- _localtime32_s
- localtime_s
- _o__localtime32_s
- _o__localtime64_s
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
- _localtime32_s
- localtime32_s
- localtime_s
- localtime64_s
- _localtime64_s
helpviewer_keywords:
- _localtime64_s function
- localtime32_s function
- _localtime32_s function
- localtime64_s function
- time, converting values
- localtime_s function
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
ms.openlocfilehash: 3c5d194da85eb5d008dfc9cf19f222ebb575747d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342120"
---
# <a name="localtime_s-_localtime32_s-_localtime64_s"></a>localtime_s、_localtime32_s、_localtime64_s

**time_t**時間値を**tm**構造体に変換し、ローカル タイム ゾーンを修正します。 これらは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) で説明されているように、セキュリティが強化されたバージョンの [localtime、_localtime32、_localtime64](localtime-localtime32-localtime64.md) です。

## <a name="syntax"></a>構文

```C
errno_t localtime_s(
   struct tm* const tmDest,
   time_t const* const sourceTime
);
errno_t _localtime32_s(
   struct tm* tmDest,
   __time32_t const* sourceTime
);
errno_t _localtime64_s(
   struct tm* tmDest,
   __time64_t const* sourceTime
);
```

### <a name="parameters"></a>パラメーター

*tmDest*<br/>
目的の情報を格納する時間構造体へのポインター。

*ソースタイム*<br/>
格納されている時刻へのポインター。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。 障害が発生した場合、戻り値はエラー コードを示します。 エラー コードは、Errno.h で定義されています。 これらのエラー一覧については、「[errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

### <a name="error-conditions"></a>エラー条件

|*tmDest*|*ソースタイム*|戻り値|*tmDest の*値|無効なパラメーター ハンドラーを呼び出す|
|-----------|------------|------------------|--------------------|---------------------------------------|
|**NULL**|any|**Einval**|変更されない|はい|
|**NULL**でない (有効なメモリを指す)|**NULL**|**Einval**|すべてのフィールドが -1 に設定される|はい|
|**NULL**でない (有効なメモリを指す)|0 未満または **_MAX__TIME64_T**より大きい|**Einval**|すべてのフィールドが -1 に設定される|いいえ|

最初の 2 つのエラーの場合は、「[Parameter Validation](../../c-runtime-library/parameter-validation.md)」 (パラメーターの検証) に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、これらの関数は**errno**を**EINVAL**に設定し **、EINVAL**を返します。

## <a name="remarks"></a>解説

**localtime_s**関数は、time_t[値として](../../c-runtime-library/standard-types.md)格納された時刻を変換し、その結果を[tm](../../c-runtime-library/standard-types.md)型の構造体に格納します。 **time_t**値*sourceTime*は、1970 年 1 月 1 日 (UTC) 午前 0 時 (00:00:00) から経過した秒数を表します。 この値は、通常、[時間](time-time32-time64.md)関数から取得されます。

**localtime_s**は、ユーザーが最初にグローバル環境変数**TZ**を設定した場合に、ローカル タイム ゾーンを修正します。 **TZ**を設定すると、他の 3 つの環境変数 (**_timezone**、 **_daylight**、**および _tzname**) も自動的に設定されます。 **TZ**変数が設定されていない場合 **、localtime_s**はコントロール パネルの日付/時刻アプリケーションで指定されたタイム ゾーン情報を使用しようとします。 この情報を取得できない場合、既定では、太平洋タイム ゾーンを表す PST8PDT が使用されます。 これらの変数の説明については、[_tzset](tzset.md) を参照してください。 **TZ**はマイクロソフトの拡張機能であり、**ローカルタイム**の ANSI 標準定義の一部ではありません。

> [!NOTE]
> 対象の環境によって、夏時間が有効かどうか判断されます。

**__time64_t**構造を使用する **__time64_t**_localtime64_sは、日付を 23:59:59、3001 年 1 月 18 日(協定世界時)まで表すことができますが **、_localtime32_s**は 2038 年 1 月 18 日 (UTC) までの日付を表します。

**localtime_s**はインライン関数で **、_localtime64_s**に評価され **、time_t**は **__time64_t**と同等です。 コンパイラが古い 32 ビット**time_t**として**time_t**を解釈するようにする必要がある場合は、 **_USE_32BIT_TIME_T**を定義できます。 これを行うと **、localtime_s**は **_localtime32_s**に評価されます。 この方法はお勧めしません。2038 年 1 月 18 日より後にアプリケーションがエラーになる可能性があり、また、64 ビット プラットフォームでは使用できないためです。

構造体型[tm](../../c-runtime-library/standard-types.md)のフィールドには、次の値が格納され、各フィールドは**int**です。

|フィールド|説明|
|-|-|
|**tm_sec**|分の後の秒 (0 - 59)。|
|**tm_min**|時間後の分(0 - 59)。|
|**tm_hour**|真夜中から経過した時間 (0 - 23)。|
|**tm_mday**|月の日 (1 から 31)。|
|**tm_mon**|月 (0 - 11;1 月 = 0)。|
|**tm_year**|年 (実際の西暦から 1900 を引いた数)|
|**tm_wday**|曜日 (0 ~ 6;日曜日 = 0)。|
|**tm_yday**|年の日 (0 - 365;1月1日 = 0)。|
|**tm_isdst**|夏時間が有効な場合は正の値、夏時間が無効な場合は 0、夏時間かどうか状態が不明な場合は負の値。|

**TZ**環境変数が設定されている場合、C ランタイム ライブラリは、夏時間 (DST) の計算を実装するために米国に適した規則を想定します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須の C ヘッダー|必須の C++ ヘッダー|
|-------------|---------------------|-|
|**localtime_s**, **_localtime32_s**, **_localtime64_s**|\<time.h>|\<ctime>\<または時間.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_localtime_s.c
// This program uses _time64 to get the current time
// and then uses _localtime64_s() to convert this time to a structure
// representing the local time. The program converts the result
// from a 24-hour clock to a 12-hour clock and determines the
// proper extension (AM or PM).

#include <stdio.h>
#include <string.h>
#include <time.h>

int main( void )
{
    struct tm newtime;
    char am_pm[] = "AM";
    __time64_t long_time;
    char timebuf[26];
    errno_t err;

    // Get time as 64-bit integer.
    _time64( &long_time );
    // Convert to local time.
    err = _localtime64_s( &newtime, &long_time );
    if (err)
    {
        printf("Invalid argument to _localtime64_s.");
        exit(1);
    }
    if( newtime.tm_hour > 12 )        // Set up extension.
        strcpy_s( am_pm, sizeof(am_pm), "PM" );
    if( newtime.tm_hour > 12 )        // Convert from 24-hour
        newtime.tm_hour -= 12;        // to 12-hour clock.
    if( newtime.tm_hour == 0 )        // Set hour to 12 if midnight.
        newtime.tm_hour = 12;

    // Convert to an ASCII representation.
    err = asctime_s(timebuf, 26, &newtime);
    if (err)
    {
        printf("Invalid argument to asctime_s.");
        exit(1);
    }
    printf( "%.19s %s\n", timebuf, am_pm );
}
```

```Output
Fri Apr 25 01:19:27 PM
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime_s、_wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime、_ftime32、_ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s、_gmtime32_s、_gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime、_localtime32、_localtime64](localtime-localtime32-localtime64.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
