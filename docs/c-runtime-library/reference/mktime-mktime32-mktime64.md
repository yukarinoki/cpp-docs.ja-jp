---
title: mktime、_mktime32、_mktime64
ms.date: 4/2/2020
api_name:
- _mktime32
- mktime
- _mktime64
- _o__mktime32
- _o__mktime64
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
- mktime
- _mktime64
helpviewer_keywords:
- _mktime32 function
- mktime function
- time functions
- mktime64 function
- converting times
- mktime32 function
- _mktime64 function
- time, converting
ms.assetid: 284ed5d4-7064-48a2-bd50-15effdae32cf
ms.openlocfilehash: b0981f33d70945083eacd28eb7517e80b3f2539f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338704"
---
# <a name="mktime-_mktime32-_mktime64"></a>mktime、_mktime32、_mktime64

現地時刻をカレンダーの値に変換します。

## <a name="syntax"></a>構文

```C
time_t mktime(
   struct tm *timeptr
);
__time32_t _mktime32(
   struct tm *timeptr
);
__time64_t _mktime64(
   struct tm *timeptr
);
```

### <a name="parameters"></a>パラメーター

*timeptr*<br/>
時間構造体へのポインター。「[asctime](asctime-wasctime.md)」をご覧ください。

## <a name="return-value"></a>戻り値

**_mktime32**は、指定された暦時刻を型[time_t](../../c-runtime-library/standard-types.md)の値としてエンコードして返します。 *timeptr*が 1970 年 1 月 1 日の午前 0 時より前の日付を参照する場合、またはカレンダー時刻を表すことができない場合 **、_mktime32**は -1 キャストを**time_t**に戻します。 **_mktime32**を使用し *、timeptr*が 2038 年 1 月 18 日 23:59:59 以降の日付を参照する場合、-1 キャストを**time_t。**

*timeptr*が 3000 年 12 月 31 日(UTC) 23:59:59 以降の日付を参照する場合 **、_mktime64**はタイプ **__time64_t**に -1 キャストを返します。

## <a name="remarks"></a>解説

**mktime、_mktime32、****および_mktime64**関数は *、timeptr*によって指し示される時刻構造 (おそらく不完全) を、正規化された値を持つ完全に定義された構造に変換し、それを**time_t**の暦時刻値に変換します。 **_mktime32** 変換された時間のエンコーディングは、[time](time-time32-time64.md) 関数によって返される値と同じエンコーディングになります。 *timeptr*構造体の**tm_wday**と**tm_yday**コンポーネントの元の値は無視され、他のコンポーネントの元の値は通常の範囲に制限されません。

**mktime**は、 **_USE_32BIT_TIME_T**定義されていない限り **、 _mktime64**と等価なインライン関数 **_mktime32。**

UTC に調整した後 **、_mktime32は**1970 年 1 月 1 日午前 0 時から 2038 年 1 月 18 日 23:59:59 までを処理します。 **_mktime64**は、1970 年 1 月 1 日午前 0 時から 3000 年 12 月 31 日 23:59:59 まで、日付を処理します。 この調整により、指定した日付が範囲内にある場合でも、これらの関数は -1 **(time_t**、 **__time32_t、****または __time64_t**) を返す可能性があります。 たとえば、エジプトのカイロにいる場合は、UTC より 2 時間進んでいるので、*timeptr* で指定した日付から最初に 2 時間が差し引かれます。そのため、日付が範囲外になる可能性があります。

これらの関数は、tm 構造体の検証と値の設定に使用されることがあります。 正常に実行された場合、これらの関数は **、tm_wday**と**tm_yday**の値を適切に設定し、指定された暦時刻を表す他のコンポーネントを設定しますが、その値は通常の範囲に強制的に設定されます。 **tm_mday**の最終的な値は **、tm_mon**と**tm_year**が決定されるまで設定されません。 **tm**構造時間を指定する場合は **、tm_isdst**フィールドを次のように設定します。

- 標準時間が有効であることを示す場合はゼロ (0)。

- 夏時間が有効であることを示す場合は 0 より大きい値。

- 標準時間と夏時間のどちらが有効であるかを C ランタイム ライブラリ コードで計算する場合は 0 より小さい値。

C ランタイム ライブラリは、[TZ](tzset.md) 環境変数から夏時間の状態を判断します。 **TZ**が設定されていない場合は、オペレーティング システムから夏時間情報を取得するために Win32 API 呼び出し[GetTimeZoneInformation](/windows/win32/api/timezoneapi/nf-timezoneapi-gettimezoneinformation)が使用されます。 これが失敗すると、ライブラリは、夏時間の計算の実装にアメリカ合衆国の規則が使用されると見なします。 **tm_isdst**は必須フィールドです。 設定しないと、その値は未定義になり、これらの関数からは予想外の値が返されます。 *timeptr*が[asctime](asctime-wasctime.md)、 [gmtime](gmtime-gmtime32-gmtime64.md)、または[localtime](localtime-localtime32-localtime64.md) (またはこれらの関数のバリアント) への以前の呼び出しによって返された**tm**構造体を指している場合 **、tm_isdst**フィールドには正しい値が含まれます。

**gmtime**および**localtime** ( および **_gmtime32**、 **_gmtime64**、 **_localtime32**、**および _localtime64**) は、変換にスレッドごとに 1 つのバッファーを使用します。 このバッファを**mktime** **、_mktime32、** または **_mktime64**に渡した場合、以前の内容は破棄されます。

これらの関数では、パラメーターの検証が行われます。 *timeptr* が null ポインターである場合は、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、関数は -1 を返し **、errno**を**EINVAL**に設定します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**mktime**|\<time.h>|
|**_mktime32**|\<time.h>|
|**_mktime64**|\<time.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_mktime.c
/* The example takes a number of days
* as input and returns the time, the current
* date, and the specified number of days.
*/

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm  when;
   __time64_t now, result;
   int        days;
   char       buff[80];

   time( &now );
   _localtime64_s( &when, &now );
   asctime_s( buff, sizeof(buff), &when );
   printf( "Current time is %s\n", buff );
   days = 20;
   when.tm_mday = when.tm_mday + days;
   if( (result = mktime( &when )) != (time_t)-1 ) {
      asctime_s( buff, sizeof(buff), &when );
      printf( "In %d days the time will be %s\n", days, buff );
   } else
      perror( "mktime failed" );
}
```

### <a name="sample-output"></a>サンプル出力

```Output
Current time is Fri Apr 25 13:34:07 2003

In 20 days the time will be Thu May 15 13:34:07 2003
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime、_wasctime](asctime-wasctime.md)<br/>
[gmtime、_gmtime32、_gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime、_localtime32、_localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime、_mkgmtime32、_mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
