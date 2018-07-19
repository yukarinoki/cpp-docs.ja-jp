---
title: localtime、_localtime32、_localtime64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _localtime64
- _localtime32
- localtime
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
- localtime64
- _localtime64
- localtime32
- localtime
- _localtime32
dev_langs:
- C++
helpviewer_keywords:
- localtime32 function
- _localtime32 function
- _localtime64 function
- localtime64 function
- localtime function
- time, converting values
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 778b2d214551c5848dd091e33dbbab1814544fb4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405511"
---
# <a name="localtime-localtime32-localtime64"></a>localtime、_localtime32、_localtime64

時刻値を変換し、ローカル タイム ゾーンに合わせて修正します。 これらの関数にはセキュリティを強化したバージョンがあります。[localtime_s、_localtime32_s、_localtime64_s](localtime-s-localtime32-s-localtime64-s.md) を参照してください。

## <a name="syntax"></a>構文

```C
struct tm *localtime( const time_t *sourceTime );
struct tm *_localtime32( const __time32_t *sourceTime );
struct tm *_localtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>パラメーター

*sourceTime*<br/>
格納されている時刻へのポインター。

## <a name="return-value"></a>戻り値

構造の結果にポインターを返すまたは**NULL**日付が関数に渡される場合は。

- 1970 年 1 月 1 日午前 0 時より前。

- UTC 2038 年 1 月 19 日 03時 14分: 07 秒後 (を使用して **_time32**と**time32_t**)。

- UTC 3000 年 12 月 31 日 23時 59分: 59 秒後 (を使用して **_time64**と **_ _time64_t**)。

**_localtime64**が使用される、 **_ _time64_t**構造体、ことができますを世界協定時刻 (UTC) で 3000 年 12 月 31 日 23時 59分: 59 秒を表現する日付 **_localtime32**2038 年 1 月 18 日 23時 59分: 59 までの日付を表します。

**localtime**に評価されるインライン関数は、 **_localtime64**、および**time_t**は等価 **_ _time64_t**です。 強制的に、コンパイラを解釈する必要がある場合**time_t**古い 32 ビットとして**time_t**を定義できます **_USE_32BIT_TIME_T**です。 これにより、その**localtime**を評価する **_localtime32**です。 ただし、この方法は推奨されません。2038 年 1 月 18 日以降にアプリケーションがエラーになる可能性があり、また、64 ビット プラットフォームでは使用できないためです。

構造体型のフィールドの[tm](../../c-runtime-library/standard-types.md)それぞれが、次の値を格納、 **int**:

|フィールド|説明|
|-|-|
|**tm_sec**|秒 (0 ~ 59)。|
|**未満**|分 (0 ~ 59)。|
|**tm_hour**|午前 0 時からの経過時間 (0 ~ 23)。|
|**tm_mday**|(1 ~ 31) の月の日です。|
|**表します。**|月 (0 ~ 11 です。年 1 月 = 0) です。|
|**tm_year**|年 (実際の西暦から 1900 を引いた数)|
|**tm_wday**|曜日 (0 ~ 6 です。日曜日 = 0) です。|
|**tm_yday**|年の日付 (0 ~ 365 です。1 月 1 日 = 0) です。|
|**tm_isdst**|夏時間が有効な場合は正の値、夏時間が無効な場合は 0、夏時間かどうか状態が不明な場合は負の値。|

場合、 **TZ**環境変数の設定を C ランタイム ライブラリの規則 United States に適切な夏時間 (DST) の計算を実装するためです。

## <a name="remarks"></a>コメント

**Localtime**関数として格納されている時刻の変換、 [time_t](../../c-runtime-library/standard-types.md)値し、型の構造体に結果を格納[tm](../../c-runtime-library/standard-types.md)です。 **長い**値*sourceTime*午前 0 時以降の経過秒数を表します (00: 00:00)、1970 年 1 月 1 日 (utc)。 通常、この値はから取得、[時間](time-time32-time64.md)関数。

32 ビットおよび 64 ビット バージョンの両方[gmtime](gmtime-gmtime32-gmtime64.md)、 [mktime](mktime-mktime32-mktime64.md)、 [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md)、および**localtime** 、1 つを使用してすべて**tm**変換のスレッドあたりの構造体。 これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。

**localtime** 、ユーザーが最初に、グローバル環境変数を設定する場合は、ローカル タイム ゾーンの修正**TZ**です。 ときに**TZ**設定すると、その他の 3 つの環境変数 (**_timezone**、 **_daylight**、および **_tzname**) も自動的に設定します。 場合、 **TZ**変数が設定されていない**localtime**コントロール パネルの 日付/時刻で指定されているタイム ゾーン情報を使用しようとしています。 この情報を取得できない場合、既定では、太平洋タイム ゾーンを表す PST8PDT が使用されます。 これらの変数の説明については、[_tzset](tzset.md) を参照してください。 **TZ**は Microsoft 拡張機能との ANSI 標準の定義の一部ではない**localtime**です。

> [!NOTE]
> 対象の環境は、夏時間が有効かどうかを判断しようとします。

これらの関数では、パラメーターの検証が行われます。 場合*sourceTime*が null ポインターの場合は、 *sourceTime*値が負の値、」の説明に従って、これらの関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md). 関数を返すかどうかは、引き続き実行が許可された、 **NULL**設定と**errno**に**EINVAL**です。

## <a name="requirements"></a>要件

|ルーチン|必須の C ヘッダー|必須の C++ ヘッダー|
|-------------|---------------------|-|
|**localtime**、 **_localtime32**、 **_localtime64**|\<time.h>|\<ctime > または\<time.h >|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
