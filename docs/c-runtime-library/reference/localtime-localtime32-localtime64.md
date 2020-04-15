---
title: localtime、_localtime32、_localtime64
ms.date: 4/2/2020
api_name:
- _localtime64
- _localtime32
- localtime
- _o__localtime32
- _o__localtime64
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
- localtime64
- _localtime64
- localtime32
- localtime
- _localtime32
helpviewer_keywords:
- localtime32 function
- _localtime32 function
- _localtime64 function
- localtime64 function
- localtime function
- time, converting values
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
ms.openlocfilehash: 21496b71c354c7bed7b87526dc40bc9b24865da2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342138"
---
# <a name="localtime-_localtime32-_localtime64"></a>localtime、_localtime32、_localtime64

時刻値を変換し、ローカル タイム ゾーンに合わせて修正します。 これらの関数にはセキュリティを強化したバージョンがあります。[localtime_s、_localtime32_s、_localtime64_s](localtime-s-localtime32-s-localtime64-s.md) を参照してください。

## <a name="syntax"></a>構文

```C
struct tm *localtime( const time_t *sourceTime );
struct tm *_localtime32( const __time32_t *sourceTime );
struct tm *_localtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>パラメーター

*ソースタイム*<br/>
格納されている時刻へのポインター。

## <a name="return-value"></a>戻り値

構造体の結果へのポインターを返すか、関数に渡された日付が**NULL の**場合は NULL を返します。

- 1970 年 1 月 1 日午前 0 時より前。

- 2038年1月19日 03:14:07 以降、UTC **(_time32**と**time32_t**を使用)。

- 23:59:59、3000 年 12 月 31 日、UTC **(_time64**および **__time64_t**を使用)。

**__time64_t**構造を使用する **__time64_t**_localtime64では、日付を 23:59:59、3000 年 12 月 31 日(協定世界時)、_localtime32は 2038 年 1 月 18 日 23:59:59**まで表します**。

**localtime**は _localtime64**と評価**されるインライン関数で **、time_t**は **__time64_t**と同等です。 コンパイラが古い 32 ビット**time_t**として**time_t**を解釈するようにする必要がある場合は、 **_USE_32BIT_TIME_T**を定義できます。 これを行うと、**ローカルタイム**は **_localtime32**に評価されます。 この方法はお勧めしません。2038 年 1 月 18 日より後にアプリケーションがエラーになる可能性があり、また、64 ビット プラットフォームでは使用できないためです。

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

## <a name="remarks"></a>解説

**localtime**関数は、格納された時刻を[time_t](../../c-runtime-library/standard-types.md)値として変換し、その結果を[tm](../../c-runtime-library/standard-types.md)型の構造体に格納します。 **長い**値*の sourceTime*は、1970 年 1 月 1 日 (UTC) 午前 0 時 (00:00:00) から経過した秒数を表します。 この値は、通常、[時間](time-time32-time64.md)関数から取得されます。

32 ビットバージョンと 64 ビットバージョンの[gmtime、mktime、mkgmtime、](gmtime-gmtime32-gmtime64.md)および**localtime**の両方のバージョンでは、変換にスレッドごとに 1 つの**tm**構造体を使用します。 [mktime](mktime-mktime32-mktime64.md) [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md) これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。

ユーザーが最初にグローバル環境変数**TZ**を設定した場合 **、localtime**はローカルタイムゾーンを修正します。 **TZ**を設定すると、他の 3 つの環境変数 (**_timezone**、 **_daylight**、**および _tzname**) も自動的に設定されます。 **TZ**変数が設定されていない場合 **、localtime**はコントロール パネルの日付/時刻アプリケーションで指定されたタイム ゾーン情報を使用しようとします。 この情報を取得できない場合、既定では、太平洋タイム ゾーンを表す PST8PDT が使用されます。 これらの変数の説明については、[_tzset](tzset.md) を参照してください。 **TZ**はマイクロソフトの拡張機能であり、**ローカルタイム**の ANSI 標準定義の一部ではありません。

> [!NOTE]
> 対象の環境によって、夏時間が有効かどうか判断されます。

これらの関数では、パラメーターの検証が行われます。 *sourceTime*が null ポインターの場合、または*sourceTime*値が負の場合、これらの関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、関数は**NULL を**返し **、errno**を**EINVAL**に設定します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須の C ヘッダー|必須の C++ ヘッダー|
|-------------|---------------------|-|
|**現地 ,** **_localtime32**, **_localtime64**|\<time.h>|\<ctime>\<または時間.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_localtime.cpp
// compile with: /W3
// This program uses _time64 to get the current time
// and then uses localtime64() to convert this time to a structure
// representing the local time. The program converts the result
// from a 24-hour clock to a 12-hour clock and determines the
// proper extension (AM or PM).

#include <stdio.h>
#include <string.h>
#include <time.h>

int main( void )
{
    struct tm *newtime;
    char am_pm[] = "AM";
    __time64_t long_time;

    _time64( &long_time );             // Get time as 64-bit integer.
                                       // Convert to local time.
    newtime = _localtime64( &long_time ); // C4996
    // Note: _localtime64 deprecated; consider _localetime64_s

    if( newtime->tm_hour > 12 )        // Set up extension.
        strcpy_s( am_pm, sizeof(am_pm), "PM" );
    if( newtime->tm_hour > 12 )        // Convert from 24-hour
        newtime->tm_hour -= 12;        //   to 12-hour clock.
    if( newtime->tm_hour == 0 )        // Set hour to 12 if midnight.
        newtime->tm_hour = 12;

    char buff[30];
    asctime_s( buff, sizeof(buff), newtime );
    printf( "%.19s %s\n", buff, am_pm );
}
```

```Output
Tue Feb 12 10:05:58 AM
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime、_wasctime](asctime-wasctime.md)<br/>
[ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime、_ftime32、_ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime、_gmtime32、_gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime_s、_localtime32_s、_localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
