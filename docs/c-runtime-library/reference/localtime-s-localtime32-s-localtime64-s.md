---
title: localtime_s、_localtime32_s、_localtime64_s
ms.date: 11/04/2016
apiname:
- _localtime64_s
- _localtime32_s
- localtime_s
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
ms.openlocfilehash: 44b2eb2515035d56143a2aab251437a92515e652
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157290"
---
# <a name="localtimes-localtime32s-localtime64s"></a>localtime_s、_localtime32_s、_localtime64_s

変換を**time_t**時刻の値を**tm**構造体、およびローカル タイム ゾーンに合わせて修正します。 これらは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) で説明されているように、セキュリティが強化されたバージョンの [localtime、_localtime32、_localtime64](localtime-localtime32-localtime64.md) です。

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

*sourceTime*<br/>
格納されている時刻へのポインター。

## <a name="return-value"></a>戻り値

正常終了した場合は 0。 障害が発生した場合、戻り値はエラー コードを示します。 エラー コードは、Errno.h で定義されています。 これらのエラー一覧については、「[errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

### <a name="error-conditions"></a>エラー条件

|*tmDest*|*sourceTime*|戻り値|値*tmDest*|無効なパラメーター ハンドラーを呼び出す|
|-----------|------------|------------------|--------------------|---------------------------------------|
|**NULL**|任意|**EINVAL**|変更されない|はい|
|いない**NULL** (有効なメモリを指す)|**NULL**|**EINVAL**|すべてのフィールドが -1 に設定される|[はい]|
|いない**NULL** (有効なメモリを指す)|0 より小さいかより大きい **_MAX__TIME64_T**|**EINVAL**|すべてのフィールドが -1 に設定される|いいえ|

最初の 2 つのエラーの場合は、「[Parameter Validation](../../c-runtime-library/parameter-validation.md)」 (パラメーターの検証) に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**戻って**EINVAL**します。

## <a name="remarks"></a>Remarks

**_Localtime32_s**関数として格納されている時刻の変換、 [time_t](../../c-runtime-library/standard-types.md)値し、その結果の種類の構造に格納[tm](../../c-runtime-library/standard-types.md)します。 **長い**値*sourceTime*午前 0 時以降の経過秒数を表します (00: 00:00)、UTC 1970 年 1 月 1 日です。 通常、この値はから取得、[時間](time-time32-time64.md)関数。

**_localtime32_s** 、ユーザーが最初にグローバル環境変数を設定する場合、ローカル タイム ゾーンに合わせて修正**TZ**します。 ときに**TZ**設定は、その他の 3 つの環境変数 (**_timezone**、 **_daylight**、および **_tzname**) も自動的に設定します。 場合、 **TZ**変数が設定されていない**localtime32_s**コントロール パネルの 日付/時刻で指定されているタイム ゾーン情報を使用します。 この情報を取得できない場合、既定では、太平洋タイム ゾーンを表す PST8PDT が使用されます。 これらの変数の説明については、[_tzset](tzset.md) を参照してください。 **TZ**は Microsoft 拡張機能との ANSI 標準定義の一部ではない**localtime**します。

> [!NOTE]
> 対象の環境は、夏時間が有効かどうかを判断しようとします。

**_localtime64_s**、使用、 **_ _time64_t**構造体、ことができますを 23時 59分: 59、1 月 18 日、3001、世界協定時刻 (UTC) を表す日付 **_localtime32_s**2038 年 1 月 18 日 23時 59分: 59 までの日付を表します。

**localtime_s**に評価されるインライン関数は、 **_localtime64_s**、および**time_t**と等価 **_ _time64_t**します。 強制的にコンパイラを解釈する必要がある場合**time_t**古い 32 ビットとして**time_t**を定義できます **_USE_32BIT_TIME_T**します。 これにより**localtime_s**を評価する **_localtime32_s**します。 ただし、この方法は推奨されません。2038 年 1 月 18 日以降にアプリケーションがエラーになる可能性があり、また、64 ビット プラットフォームでは使用できないためです。

構造体型のフィールド[tm](../../c-runtime-library/standard-types.md)はそれぞれ、次の値を格納、 **int**します。

|フィールド|説明|
|-|-|
|**tm_sec**|秒 (0 - 59)。|
|**tm_min**|分 (0 - 59)。|
|**tm_hour**|午前 0 時からの経過時間 (0 - 23)。|
|**tm_mday**|(1 ~ 31) の月の日。|
|**tm_mon**|月 (0 - 11年 1 月 = 0 です)。|
|**tm_year**|年 (実際の西暦から 1900 を引いた数)|
|**tm_wday**|週の曜日 (0 ~ 6 です。日曜日 = 0)。|
|**tm_yday**|年の通算日 (0 - 365;1 月 1 日 = 0)。|
|**tm_isdst**|夏時間が有効な場合は正の値、夏時間が無効な場合は 0、夏時間かどうか状態が不明な場合は負の値。|

場合、 **TZ**環境変数が設定されている、C ランタイム ライブラリで規則を前提を米国に適切な夏時間 (DST) の計算の実装します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須の C ヘッダー|必須の C++ ヘッダー|
|-------------|---------------------|-|
|**localtime_s**、 **_localtime32_s**、 **_localtime64_s**|\<time.h>|\<ctime > または\<time.h >|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
